[English](README.md) · **简体中文**

> 英文版是规范版本。本页与 [README.md](README.md) 不一致时，以英文版为准。

<!-- translation-of: README.md sha256:6c4b32b46e9276ba -->

<!-- Source: Best-README-Template BLANK_README (Unlicense) — https://github.com/othneildrew/Best-README-Template -->
<a id="readme-top"></a>

# Problems

一个已归档的个人笔记仓库，唯一的内容是一篇带日期的中文笔记，分析了 AI 编码代理为何会绕过 spec→plan→code 工作流程，并记录了已评估但仍搁置、等待更好方案的候选修复思路。

[![License](https://img.shields.io/github/license/anyingiit/Problems)](LICENSE)

[报告问题](https://github.com/anyingiit/Problems/issues/new?template=bug_report.yml) · [提出需求](https://github.com/anyingiit/Problems/issues/new?template=feature_request.yml)

<details>
  <summary>目录</summary>
  <ol>
    <li><a href="#about-the-project">关于本项目</a></li>
    <li><a href="#getting-started">开始使用</a></li>
    <li><a href="#usage">用法</a></li>
    <li><a href="#contributing">参与贡献</a></li>
    <li><a href="#license">许可证</a></li>
    <li><a href="#contact">联系方式</a></li>
  </ol>
</details>

## 关于本项目

Problems 是 anyingiit 的个人仓库之一。GitHub 上该仓库已被标记为归档，其全部内容只有一个文件 `2026-08-24-ai-agent-workflow-discipline.md`——一篇带日期的中文笔记，记录了一个反复出现的问题：AI 编码代理（笔记中点名的是 OpenCode 加 superpowers 技能集）有时会跳过预期的 spec → plan → code 纪律，先写 plan 再倒推 spec，或者干脆忘记调用本该强制这一顺序的技能。笔记从两个层面梳理了可能的成因——它引用的文献所记录的"指令漂移"和"Lost in the Middle"效应，以及提示词层规则相对于机械门禁的实际局限——并列出了已评估的五种候选方案（提示词文件、路径级权限、插件层工具拦截、专门的状态机工具，以及让第二个 LLM 充当审核员），逐一说明各自的不足，最终得出结论：目前尝试过的方案都还不够理想。笔记自己的状态行将其标记为"搁置"，只有在出现更根本的解决方案时才会重新评估。

除此之外没有练习、源代码或其他笔记——仓库里只有这一条记录。

## 开始使用

### 环境要求

- 一个能显示中文的文本编辑器或 Markdown 查看器即可；本仓库没有任何软件包清单、依赖列表或构建配置。

### 安装

没有构建步骤，也没有任何依赖需要安装。克隆仓库即可得到笔记的本地副本：

```sh
git clone https://github.com/anyingiit/Problems.git
cd Problems
```

## 用法

用编辑器打开 `2026-08-24-ai-agent-workflow-discipline.md`，阅读其中的分析；等笔记里记录的某个触发条件成立时，也可以在其后续写补充记录：

```sh
$EDITOR 2026-08-24-ai-agent-workflow-discipline.md
```

## 参与贡献

欢迎参与。[CONTRIBUTING.md](CONTRIBUTING.md) 说明如何提交 issue 或 pull request，[CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) 说明对所有参与者的行为要求。

请不要在公开的 issue 或 pull request 中报告安全问题。[SECURITY.md](SECURITY.md) 说明了私下报告的方式。

## 许可证

以 MIT 许可证分发。详见 [LICENSE](LICENSE)。

## 联系方式

项目地址：[https://github.com/anyingiit/Problems](https://github.com/anyingiit/Problems)

<p align="right">(<a href="#readme-top">back to top</a>)</p>
