# Plan Output Template / 方案输出模板

Use this template after inspecting both the design platform and the current repository. / 在读取设计平台页面和当前仓库后，按此模板输出分析结果。

## 1. Target Confirmation / 目标确认

- Design link / 设计稿链接
- Design platform or domain / 设计平台名称或域名
- Target page, route, or component named by the user / 用户指定的目标页面、路由或组件
- Resolved repository path or directory / 解析到的仓库路径或目录

## 2. Design Extraction / 设计提取结果

- UI structure breakdown / UI 结构拆解
- Dimensions and spacing backed by structured values / 有结构化标注支撑的尺寸与间距
- Typography backed by structured values / 有结构化标注支撑的字体排版
- Colors, borders, radius, and shadows backed by structured values / 有结构化标注支撑的颜色、边框、圆角和阴影
- Images, icons, or other assets / 图片、图标或其他资源
- Short note separating structured facts from visual inference / 简短说明哪些是结构化事实，哪些是视觉推断

## 3. Implementation Placement / 实现落点判断

- Changes that belong in the target page / 应落在目标页面的改动
- Changes that belong in nearby business components / 应落在周边业务组件的改动
- Existing shared components that should be reused / 应复用的现有公共组件
- Changes that need shared styles, tokens, or theme updates / 需要触达公共样式、token 或主题层的改动

## 4. Planned File Changes / 计划修改文件

- Existing files to modify / 需要修改的现有文件
- New files to add, if necessary / 如有必要，需要新增的文件
- Short reason for each file / 每个文件为什么要改的简短说明

## 5. Risks And Tradeoffs / 风险与取舍

- Missing structured values / 缺失的结构化标注值
- Missing access, mode, or permission prerequisites / 缺失的平台权限、模式或访问前提
- Conflicts with current repository patterns or tokens / 与现有仓库模式或 token 的冲突
- Mismatches between design structure and current implementation structure / 设计结构与当前实现结构不一致的地方
- Non-UI implications hidden in the design / 设计稿暗含的非 UI 改动

## 6. Confirmation Close / 确认口

End with one direct sentence that makes it clear implementation has not started yet. / 最后用一句直接的话明确表示尚未开始改代码。

Recommended close: / 推荐收尾语：

`This is the implementation plan. Confirm and I will start the code changes. / 以上是实现方案，确认后我再开始修改代码。`
