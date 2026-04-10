# design-to-page

Turn a design link into a repo-aware frontend implementation plan before coding.  
在开始编码之前，把设计稿链接转成结合仓库结构的前端实现方案。

`design-to-page` is a bilingual Codex skill for design-driven frontend work. It opens the design in a controlled browser, waits for the user to complete any password or login steps inside that page, extracts structured design facts, maps them to the current codebase, and stops at a concrete implementation plan before any code changes.  
`design-to-page` 是一个面向设计稿驱动前端开发的中英双语 Codex skill。它会在受控浏览器中打开设计稿，等待用户在页面内完成密码或登录步骤，提取结构化设计信息，映射到当前代码仓库，并在任何代码修改前先停在明确的实现方案阶段。

## Why This Skill / 为什么需要这个 Skill

Design-to-code tasks often fail for predictable reasons:

- The agent starts coding before understanding the repository structure. / 还没看懂仓库结构就开始改代码。
- Design facts are guessed from screenshots instead of read from inspect data. / 靠截图目测猜数值，而不是读取结构化标注。
- Passwords or login flows are handled in chat instead of inside the controlled browser. / 在对话里处理密码或登录，而不是在受控浏览器中完成。
- The implementation jumps straight to code without an explicit plan. / 跳过实现方案，直接进入编码。

`design-to-page` is built to prevent those failures by enforcing a stricter workflow.  
`design-to-page` 的目标就是通过更严格的工作流避免这些问题。

## What It Guarantees / 它保证什么

- Repository-first analysis before implementation. / 先看仓库，再谈实现。
- Structured inspect/spec values are treated as the source of truth when available. / 有结构化标注时，以其作为事实来源。
- Passwords, credentials, and verification codes are never requested in chat. / 不会要求用户把密码、登录凭据或验证码发到对话里。
- The skill stops at an implementation plan and waits for explicit confirmation before coding. / 会停在实现方案阶段，等待用户明确确认后再开始改代码。

## Best For / 最适合的场景

- Matching an existing page to a design link. / 让已有页面对齐设计稿。
- Restyling a route or component from a prototype. / 根据原型改造某个路由或组件。
- Planning design implementation in a real repository before code changes. / 在真实仓库中先规划设计落地方案，再开始编码。

## Not For / 不适合的场景

- General design review with no implementation target. / 没有具体实现目标的泛设计评审。
- Screenshot-only or export-only tasks. / 只做截图、导出之类的任务。
- Work that depends on guessing pixel values from images. / 依赖从截图里猜像素值的任务。

## Requirements / 使用前提

- A controlled browser is available, such as Chrome DevTools MCP or an equivalent browser-control tool. / 需要可用的受控浏览器，例如 Chrome DevTools MCP 或等价浏览器控制工具。
- The target repository is available for inspection. / 需要可以读取目标仓库。
- The user can complete passwords, login, and verification inside the controlled browser page. / 用户可以在受控浏览器页面内完成密码、登录和验证码操作。

## Install / 安装方式

If this repository is published to GitHub, install the skill from the path `skills/design-to-page`.  
如果这个仓库发布到了 GitHub，请从 `skills/design-to-page` 路径安装这个 skill。

Example with Codex skill installer:

```text
Use $skill-installer to install this skill from <owner>/<repo> path skills/design-to-page.
```

After installation, restart Codex so the skill is discovered.  
安装后重启 Codex，让 skill 被重新发现。

## Example Prompt / 使用示例

```text
Use $design-to-page to inspect this design link in the controlled browser, map it to my repo, and produce an implementation plan before any code changes.
```

## Workflow Summary / 工作流摘要

1. Validate that the request is really design-to-implementation work. / 先确认请求确实属于“设计稿到实现”任务。
2. Inspect the repository and locate the target page, route, or component. / 检查仓库并定位目标页面、路由或组件。
3. Open the design link in the controlled browser. / 在受控浏览器中打开设计稿链接。
4. If blocked by password, login, or verification, wait for the user to complete it inside that page. / 如果被密码、登录或验证码阻塞，就等待用户在该页面内完成。
5. Read structured inspect/spec values when available. / 优先读取结构化标注或规格数据。
6. Map the design to the repository architecture. / 将设计要求映射到仓库结构。
7. Output a concrete implementation plan and stop for confirmation. / 输出明确的实现方案，并停下来等待确认。

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

## Publishing / 发布说明

See [PUBLISHING.md](./PUBLISHING.md) for a minimal release checklist and installation-path guidance.  
发布和维护说明见 [PUBLISHING.md](./PUBLISHING.md)。

## License / 许可证

This repository is licensed under Apache-2.0. See [LICENSE](./LICENSE).  
本仓库使用 Apache-2.0 许可证，详见 [LICENSE](./LICENSE)。
