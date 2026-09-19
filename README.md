<!-- Source: Best-README-Template BLANK_README (Unlicense) — https://github.com/othneildrew/Best-README-Template -->
<a id="readme-top"></a>

# Problems

An archived personal-notes repository whose only content is a single dated Chinese-language note analyzing why AI coding agents skip the spec-plan-code workflow, together with the candidate fixes it evaluated and shelved pending a better solution.

**English** · [简体中文](README.zh-CN.md)

[![License](https://img.shields.io/github/license/anyingiit/Problems)](LICENSE)

[Report a bug](https://github.com/anyingiit/Problems/issues/new?template=bug_report.yml) · [Request a feature](https://github.com/anyingiit/Problems/issues/new?template=feature_request.yml)

<details>
  <summary>Table of Contents</summary>
  <ol>
    <li><a href="#about-the-project">About The Project</a></li>
    <li><a href="#getting-started">Getting Started</a></li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
  </ol>
</details>

## About The Project

Problems is one of anyingiit's personal repositories. GitHub lists it as archived, and its entire content is a single file, `2026-08-24-ai-agent-workflow-discipline.md`, a dated note (in Chinese) that records a recurring failure: AI coding agents (the note names OpenCode plus the superpowers skill set) sometimes skip the intended spec → plan → code discipline, write a plan before a spec and then back-fill the spec to match it, or simply forget to invoke the skills meant to enforce the sequence. The note works through the likely causes at two levels — instruction drift and "lost in the middle" effects documented in the literature it cites, and the practical limits of prompt-only rules versus mechanical gates — tabulates five candidate fixes it evaluated (prompt files, path permissions, plugin-level tool gating, a dedicated state-machine tool, and a second LLM acting as auditor) with each one's shortcomings, and concludes that no solution it tried is good enough yet. Its own status line marks it shelved, to be revisited only if a more fundamental fix appears.

There are no exercises, source files, or other notes alongside it — just this one entry.

## Getting Started

### Prerequisites

- A text editor or Markdown viewer that can display Chinese text; the repository has no package manifest, dependency list, or build configuration of any kind.

### Installation

There is no build step and nothing to install. Cloning the repository gets you a local copy of the note:

```sh
git clone https://github.com/anyingiit/Problems.git
cd Problems
```

## Usage

Open `2026-08-24-ai-agent-workflow-discipline.md` in your editor to read the analysis or add a follow-up entry once one of its trigger conditions is met:

```sh
$EDITOR 2026-08-24-ai-agent-workflow-discipline.md
```

## Contributing

Contributions are welcome. Read [CONTRIBUTING.md](CONTRIBUTING.md) for how to open an issue or a pull request, and [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md) for the standards expected of everyone taking part.

Please do not report security issues in public issues or pull requests. [SECURITY.md](SECURITY.md) explains how to report them privately.

## License

Distributed under the MIT License. See [LICENSE](LICENSE) for details.

## Contact

Project link: [https://github.com/anyingiit/Problems](https://github.com/anyingiit/Problems)

<p align="right">(<a href="#readme-top">back to top</a>)</p>
