# 问题：AI 编码代理不遵守 spec→plan→code 流程纪律

**记录时间**: 2026-08-24
**状态**: 搁置，等待更好的解决方案
**触发条件**: 有从逻辑上/第一性原理上能彻底解决的方案，或有符合要求但仍不完美的方案出现时

---

## 问题描述

使用 AI 编码代理（OpenCode + superpowers）时，代理有时不遵守预期的工作流程：

1. **不先写 spec**：应该先用 brainstorming 产出 spec，但有时直接写 plan 或直接写代码
2. **倒推 spec**：写完 plan 后再补 spec，变成"用 plan 倒推 spec"，而非 spec 驱动 plan
3. **忘记调用技能**：superpowers 有 brainstorming/writing-plans 等技能，但模型有时想不起来用
4. **缺乏机械强制**：所有规则都是提示词层的，模型可以合理绕过（"这不是创造性工作"）

## 根因分析

### 学术层面（已验证）
- **指令漂移（Instruction Drift）**：LLM 对系统提示的注意力随对话轮次衰减（arXiv:2402.10962）
- **Lost in the Middle**：长上下文中部信息利用率下降（arXiv:2307.03172）
- **平坦指令模式**：LLM 没有内核/用户态指令分离，所有文本指令平等竞争（arXiv:2404.13208）

### 工具层面
- **superpowers 是纯提示词驱动**：maintainer 明确拒绝机械强制（issue #384, #1041）
- **OpenCode plugin 可以机械拦截**：但 `tool.execute.before` 对子代理可能无效（issue #5894）
- **Statewright 状态机**：支持 OpenCode 硬拦截，但需要定义工作流 JSON，与 superpowers 自由触发模式有张力

### 实证
- Claude Code 用户记录：在 6+ 处文档写"不要跳过流程"，模型在 10+ 会话中违规（issue #49259）
- 唯一可靠解法：机械门禁（PreToolUse hook 阻止工具调用），提示词无效（issue #65951）

## 已评估的方案及局限

| 方案 | 机制 | 局限 |
|---|---|---|
| AGENTS.md 提示词 | 文本规则 | 模型可能遗忘/绕过 |
| OpenCode 权限 ask/deny | 路径级文件写权限 | YOLO 模式下失效 |
| OpenCode plugin 门禁 | tool.execute.before 拦截 | 子代理可能绕过；无法做语义判断 |
| Statewright 状态机 | 工具权限按状态锁定 | 需预定义流程 JSON；与 superpowers 冲突；需注册云服务或自托管 |
| LLM 审核员（设想） | 第二个 LLM 审核流程合规 | 合规表演欺骗（准确率 0.74→0.27）；延迟；死循环风险 |

## 结论

**目前没有理想的解决方案**：
- 提示词层不可靠（学术验证）
- 机械层无法做语义判断（"这是否算新功能"）
- LLM 审核员方案概念成熟但实证有坑（欺骗、延迟、死循环）

**当前可行做法**：
- 保留 superpowers 的提示词层规则
- 人工审查作为最后防线
- 接受"偶尔漏掉"的现实

## 下次重新评估的触发条件

1. 出现从第一性原理彻底解决"LLM 不遵守流程"的方案（如新的模型架构、训练方法）
2. 出现符合要求但仍有缺陷的方案（如新的工具/框架）
3. 现有工具（superpowers/OpenCode/Statewright）推出重大更新解决此问题

## 相关链接

- superpowers: https://github.com/obra/superpowers
- Statewright: https://github.com/statewright/statewright
- OpenCode: https://opencode.ai
- 指令漂移论文: https://arxiv.org/abs/2402.10962
- Lost in the Middle: https://arxiv.org/abs/2307.03172
- LLM 审核员合规表演问题: https://arxiv.org/html/2608.14329v1
