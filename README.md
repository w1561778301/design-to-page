# design-to-page

A bilingual Codex skill for turning a design link into a repo-aware implementation plan before coding. / 一个中英双语的 Codex skill，用于把设计稿链接转化为结合仓库结构的实现方案，并在编码前先完成规划。

## What It Does / 功能说明

`design-to-page` is designed for frontend implementation work driven by design links. It opens the design in a controlled browser, waits for the user to complete any password or login steps in that browser page, extracts structured design facts, maps them to the current repository, and outputs an implementation plan before any code changes. / `design-to-page` 适用于基于设计稿链接的前端实现任务。它会在受控浏览器中打开设计稿，等待用户在页面内完成密码或登录步骤，提取结构化设计信息，映射到当前仓库，并在任何代码修改前先输出实现方案。

## Requirements / 使用前提

- A controlled browser is available, such as Chrome DevTools MCP or an equivalent browser-control tool. / 需要可用的受控浏览器，例如 Chrome DevTools MCP 或等价浏览器控制工具。
- The target repository is available for inspection. / 需要可以读取目标仓库。
- Users complete passwords, login, and verification inside the controlled browser page, not in chat. / 密码、登录和验证码需要由用户在受控浏览器页面内完成，而不是通过对话发送。

## Repository Layout / 仓库结构

```text
.
├── LICENSE
├── PUBLISHING.md
├── README.md
└── skills
    └── design-to-page
        ├── SKILL.md
        ├── agents
        │   └── openai.yaml
        └── references
            ├── design-to-page.md
            └── plan-output-template.md
```

## Install / 安装方式

If this folder is published as a GitHub repo, install the skill from the path `skills/design-to-page`. / 如果把这个目录发布成 GitHub 仓库，请从 `skills/design-to-page` 路径安装这个 skill。

Example with Codex skill installer: / 使用 Codex skill-installer 的示例：

```text
Use $skill-installer to install this skill from <owner>/<repo> path skills/design-to-page.
```

After installation, restart Codex so the new skill is discovered. / 安装后重启 Codex，让新 skill 生效。

## Example Prompt / 使用示例

```text
Use $design-to-page to inspect this design link in the controlled browser, map it to my repo, and give me an implementation plan before changing code.
```

## Behavior Guarantees / 行为约束

- The skill inspects the repository before planning. / 先检查仓库，再做实现规划。
- The skill uses structured inspect/spec values as the source of truth when available. / 优先以结构化标注或规格数据作为事实来源。
- The skill does not ask users to paste passwords, credentials, or verification codes into chat. / 不会要求用户把密码、登录凭据或验证码发到对话里。
- The skill stops at a plan and waits for explicit confirmation before coding. / 会停在实现方案阶段，等待用户明确确认后再开始编码。

## License / 许可证

This repository is licensed under Apache-2.0. See [LICENSE](./LICENSE). / 本仓库使用 Apache-2.0 许可证，详见 [LICENSE](./LICENSE)。
