# Design To Page Reference / 设计稿到页面参考

## When To Read This / 何时读取

Read this file when you need more detail about design-platform access, auth handling, inspect-panel readiness, or fact extraction. / 当你需要更详细地处理设计平台访问、鉴权、Inspect 面板可用性或事实提取时，读取本文件。

## Access Flow / 访问流程

1. Open the user-provided design URL in the controlled browser. / 用受控浏览器打开用户提供的设计稿链接。
2. Check whether the design canvas is visible. / 检查设计画布是否可见。
3. Check whether the platform's structured inspect/spec panel, or an equivalent source of concrete values, is visible. / 检查平台的结构化标注、Inspect 规格面板或等价精确数值来源是否可见。
4. If blocked by password, login, verification, or permissions, stay on that page and wait for the user to complete access there. / 如果被分享密码、登录、验证码或权限阻塞，就停在当前页面等待用户在那里完成访问。
5. Continue only after both the canvas and structured values are readable. / 只有在画布和结构化数值都可读后才继续。

## Password, Login, And Verification / 分享密码、登录与验证码

If the platform requires a password, login, or verification: / 如果页面要求分享密码、登录或验证码：

- State that you are waiting in the controlled browser. / 明确说明你正在受控浏览器中等待。
- Let the user complete the action inside the current page. / 让用户在当前页面内自行完成操作。
- If the file is share-protected, ask the user to type the password in the page itself, not in chat. / 如果是分享加密文件，让用户在页面中输入密码，而不是在对话中发送。
- Wait for the page to update after the user submits the password, login, or verification step. / 等待用户提交密码、完成登录或验证码后页面刷新。
- Re-check canvas visibility and inspect/spec availability. / 重新检查画布可见性和结构化标注是否可用。

Never ask the user to paste passwords, one-time codes, or credentials into chat. / 不要要求用户把分享密码、一次性验证码或登录凭据发送到对话里。

## Inspect Panel Readiness / 标注面板就绪检查

Before extracting values, verify that: / 在提取数值前，确认：

- The inspect/spec panel is open. / Inspect 或规格面板已打开。
- The panel contains real values, not placeholders. / 面板里显示的是真实数值，而不是空占位。
- Any required mode such as Dev Mode, Inspect Mode, or Spec Mode is enabled. / 必需的开发模式、Inspect 模式或规格模式已开启。
- The correct node or layer is selected when the platform requires selection before showing values. / 如果平台要求先选中节点才能显示数值，当前已选中正确节点。

If the panel is collapsed, try to expand it. If values are still missing, tell the user exactly which mode, panel, or node selection is missing. / 如果面板折叠，先尝试展开；如果仍然没有数值，就明确告诉用户当前缺的是哪个模式、面板或节点选择。

## Extraction Rules / 提取规则

Use structured inspect/spec data as the authority for precise values. / 将结构化标注或 Inspect 数据作为精确数值的权威来源。

Extract when available: / 有则提取：

- Width, height, and spacing relationships. / 宽高和间距关系。
- Radius, border width, and border color. / 圆角、边框宽度和边框颜色。
- Fill colors and gradients. / 填充颜色与渐变。
- Typography details. / 字体排版细节。
- Shadow and effect values. / 阴影与效果数值。
- Images, icons, and assets. / 图片、图标与资源。
- Relative layout relationships. / 相对布局关系。

Use screenshots only for hierarchy, grouping, region boundaries, and relationship checks. Do not infer exact values from screenshots. / 截图只用于理解层级、分组、区域边界和关系，不要从截图反推精确数值。

## Repository Mapping Rules / 项目映射规则

Before writing a plan, inspect the repository to identify: / 在写方案前，先检查仓库并识别：

- The target page, route, or component named by the user. / 用户指定的目标页面、路由或组件。
- Existing shared components nearby. / 周边已有的共享组件。
- Existing style files, theme layers, or token systems covering similar UI. / 覆盖类似 UI 的样式文件、主题层或 token 系统。
- Local architectural constraints that should shape implementation. / 会约束实现方式的本地架构约定。

If project conventions conflict with pixel-perfect recreation, prefer project conventions and document the tradeoff. / 如果项目约定和像素级复刻冲突，优先遵守项目约定，并把取舍写进方案。

## Blockers / 阻塞条件

Stop and report the blocker when: / 出现以下情况时停止并报告阻塞：

- The controlled-browser access flow is not complete. / 受控浏览器中的访问流程尚未完成。
- The inspect/spec panel is unavailable or unreadable. / Inspect 或规格面板不可用或不可读。
- The required mode is off, or the required node is not selected. / 没进入正确模式，或没有选中正确节点。
- The repository target cannot be found. / 找不到仓库目标。
- The design page does not match the requested target. / 设计稿页面与用户指定目标不匹配。
- Critical structured values are missing. / 关键结构化数值缺失。

## Output Discipline / 输出纪律

Before any code change, output an implementation plan grounded in repository paths and design facts. / 任何代码修改前，都必须先输出基于仓库路径和设计事实的实现方案。
