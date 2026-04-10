---
name: design-to-page
description: Plan frontend implementation from a design link before coding. Use when the user wants a specific page, route, or component to match a design or prototype and expects a repo-aware implementation plan first. / 根据设计稿或原型链接先规划前端实现方案，再开始编码。适用于用户希望某个页面、路由或组件按设计稿落地，并要求先结合仓库结构输出实现方案的场景。
---

# Design To Page / 设计稿到页面

## Purpose / 用途

Read a design in a controlled browser, extract structured design facts, map them to the current repository, and stop at an implementation plan before any code changes. / 使用受控浏览器读取设计稿，提取结构化设计信息，映射到当前仓库，并在任何代码修改前先停在“实现方案”这一步。

This skill assumes:

- A controlled browser is available, such as Chrome DevTools MCP or an equivalent browser tool. / 可使用受控浏览器，例如 Chrome DevTools MCP 或等价浏览器工具。
- The current repository is available for inspection. / 当前仓库可供检查和定位实现落点。
- If the design platform requires a password, login, or verification, the user will complete it inside the controlled browser page. / 如果设计平台要求分享密码、登录或验证码，用户会在受控浏览器页面内自行完成。

## Trigger Contract / 触发契约

Trigger this skill only when all 3 conditions are true: / 只有在以下 3 个条件同时满足时才触发：

1. The user mentions a design, prototype, or design link. / 用户提到了设计稿、原型或设计稿链接。
2. The user clearly wants implementation work, such as modify, implement, match, restore, or align with design. / 用户明确表达了实现意图，例如修改、实现、还原、对齐设计稿。
3. The user identifies a target page, route, or component. / 用户明确指出了目标页面、路由或组件。

Trigger examples: / 应触发示例：

- "Make the checkout page match this design." / “根据这个设计稿修改结账页。”
- "Use this prototype to restyle the member center page." / “参考这个原型把会员中心页面改成设计稿样式。”
- "Align the order list component to this design link." / “按这个设计稿对齐订单列表组件。”

Do not trigger for: / 以下情况不要触发：

- General design review without implementation intent. / 纯设计评审，没有实现意图。
- "Open this design link and take a look." / 只是“打开这个设计稿看看”。
- Screenshot/export-only tasks. / 只做截图、导出之类的任务。
- Requests that do not identify a specific implementation target. / 没有明确实现目标的请求。

If the request is close but incomplete, ask only for the missing design link or target page/component. / 如果请求接近但信息不完整，只补问缺失的设计稿链接或目标页面/组件。

## Required Workflow / 必须遵守的工作流

Follow this order exactly: / 必须严格按以下顺序执行：

1. Validate that the request satisfies the trigger contract. / 校验请求是否满足触发契约。
2. Inspect the repository before reading the design. / 在读取设计稿前先检查仓库。
3. Locate the target page, route, or component in the codebase. / 在代码库中定位目标页面、路由或组件。
4. Open the design platform in the controlled browser. / 用受控浏览器打开设计平台页面。
5. If access is blocked by password, login, verification, or permissions, stay on that page and wait for the user to complete it there. Do not switch to a local browser, and do not ask the user to paste passwords, verification codes, or credentials into chat. / 如果被分享密码、登录、验证码或权限阻塞，就停留在当前受控浏览器页面等待用户在那里完成操作。不要切换到本机浏览器，也不要要求用户把密码、验证码或登录凭据发到对话里。
6. Confirm that the canvas is visible and the structured inspect/spec panel is readable. / 确认设计画布可见，且结构化标注或 Inspect 规格面板可读。
7. Extract design facts primarily from structured inspect/spec data. / 以结构化标注或 Inspect 数据作为主要事实来源。
8. Keep enough page context to understand layout hierarchy and asset relationships. / 保留足够的页面上下文，用于理解层级和资源关系。
9. Map the design requirements to the repository structure. / 将设计要求映射到仓库实现结构。
10. Output an implementation plan and stop for confirmation. / 输出实现方案，并停下来等待确认。

Do not skip repository inspection, and do not start coding before the plan is confirmed. / 不要跳过仓库检查，也不要在方案确认前直接开始编码。

## Repository Inspection / 仓库检查

Read only the files needed to determine implementation placement. Identify: / 只读取完成判断所需的文件，识别以下内容：

- Tech stack and language. / 技术栈和语言。
- App entry and routing structure. / 应用入口和路由结构。
- Page and component directories. / 页面和组件目录。
- Styling system, tokens, or theme layer. / 样式系统、设计 token 或主题层。
- Existing shared components near the target area. / 目标附近已有的公共组件。

Prefer the repository's existing structure over generic abstractions. / 优先遵守仓库现有结构，而不是套用泛化抽象层。

If the target cannot be found, stop and ask the user for a more precise path or module name. / 如果找不到目标，就停止并让用户补充更精确的路径或模块名。

## Design Access And Auth / 设计访问与鉴权

Open the design URL in the controlled browser. If it is immediately readable, continue. If it is blocked by password, login, verification, or enterprise permissions, remain on the current page and wait for the user to complete access there. / 用受控浏览器打开设计链接；如果可以直接访问就继续。如果被分享密码、登录、验证码或企业权限拦住，就停在当前页面等待用户在那里完成访问。

Before continuing, both must be true: / 在继续前，下面两项都必须满足：

- The design canvas is visible. / 设计画布可见。
- The structured inspect/spec panel, or an equivalent source of concrete values, is visible and readable. / 结构化标注、Inspect 规格面板或等价的精确数值来源可见且可读。

If the platform requires entering dev mode, inspect mode, spec mode, or selecting a node before values appear, tell the user exactly what needs to be done and continue only after the values are visible. / 如果平台必须进入开发模式、Inspect 模式、规格模式，或必须先选中节点才会显示数值，就明确告诉用户下一步该做什么，并在数值可见后再继续。

## Source Of Truth / 权威来源

Treat structured inspect/spec data as the only authority for precise values. / 将结构化标注或 Inspect 规格视为精确数值的唯一权威来源。

Extract when available: / 有则提取以下信息：

- Size and spacing. / 尺寸与间距。
- Radius and borders. / 圆角与边框。
- Colors and gradients. / 颜色与渐变。
- Typography. / 字体与排版。
- Shadows and effects. / 阴影与效果。
- Images and icons. / 图片与图标。
- Layout relationships. / 布局关系。

Use screenshots or visual context only for hierarchy, grouping, and relationship checks. Do not invent precise values from visual inspection. / 截图或视觉上下文只用于理解层级、分组和关系，不要靠肉眼反推精确数值。

If a critical value is missing, record it as missing information in the plan. / 如果关键值缺失，要在方案中明确标记为缺失信息。

## Mapping To Implementation / 映射到实现层

Decide whether each change belongs in: / 判断每项改动应落在哪一层：

- The target page. / 目标页面。
- A nearby business component. / 周边业务组件。
- A shared UI component. / 公共 UI 组件。
- Shared styles, tokens, or theme infrastructure. / 公共样式、token 或主题基础设施。

Prefer minimal changes that preserve the repository's established architecture. / 优先做最小改动，并保持仓库既有架构稳定。

If the design conflicts with existing tokens, layout primitives, or component responsibilities, explain the tradeoff instead of silently overriding project conventions. / 如果设计稿和现有 token、布局原语或组件职责冲突，要在方案中说明取舍，而不是静默覆盖项目约定。

## Output Rule / 输出规则

Before changing code, read [references/plan-output-template.md](references/plan-output-template.md) and produce a structured implementation plan. / 在改代码前，先读取 [references/plan-output-template.md](references/plan-output-template.md) 并输出结构化实现方案。

The plan must include: / 方案必须包含：

- Mapping between the design target and repository target. / 设计目标与仓库目标的映射。
- Clear distinction between structured facts and visual inference. / 明确区分结构化事实和视觉推断。
- Expected files to change. / 预计修改的文件。
- Where structure and styling changes should live. / 结构和样式分别应落在哪些文件或层级。
- Risks, conflicts, and missing information. / 风险、冲突与缺失信息。
- A direct confirmation request before coding. / 编码前的明确确认口。

Do not start implementation in the same reply unless the user explicitly confirms after seeing the plan. / 除非用户在看完方案后明确确认，否则不要在同一条回复里直接开始实现。

## Blocking Conditions / 阻塞条件

Stop and report the blocker plus the user's next action when any of these is true: / 遇到以下任一情况时，停止并给出“阻塞原因 + 用户下一步动作”：

- Design access inside the controlled browser is still incomplete. / 受控浏览器中的设计访问流程尚未完成。
- The structured inspect/spec panel is unavailable or unreadable. / 结构化标注或 Inspect 面板不可用或不可读。
- The correct mode or node selection is missing. / 没进入正确模式，或没有选中正确节点。
- The repository target cannot be found. / 找不到仓库目标。
- The design content does not match the stated target. / 设计稿内容与指定目标不匹配。
- Critical design values are missing. / 关键设计数值缺失。
- The task expands beyond UI implementation into broader product or backend changes. / 任务已超出 UI 落地，扩展到更广的产品或后端改动。

Blocking messages should be short, specific, and actionable. / 阻塞提示要简短、具体、可执行。
