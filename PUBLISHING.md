# Publishing Guide / 发布说明

Use this checklist to publish `design-to-page` as a standalone public GitHub repository. / 使用以下清单将 `design-to-page` 发布为独立的公开 GitHub 仓库。

## 1. Create A Repository / 创建仓库

Create a new repository, for example `design-to-page`. / 新建一个 GitHub 仓库，例如 `design-to-page`。

## 2. Copy This Folder To Repo Root / 复制本目录到仓库根目录

Publish the contents of this folder as the repository root. The skill should remain at `skills/design-to-page`. / 将当前目录的内容作为仓库根目录发布，skill 保持在 `skills/design-to-page` 路径下。

## 3. Review Metadata / 检查元数据

Before publishing, verify: / 发布前请确认：

- `skills/design-to-page/SKILL.md` still matches the intended workflow. / `skills/design-to-page/SKILL.md` 与预期工作流一致。
- `skills/design-to-page/agents/openai.yaml` still contains the correct `display_name`, `short_description`, and `$design-to-page` default prompt. / `skills/design-to-page/agents/openai.yaml` 中的 `display_name`、`short_description` 和带 `$design-to-page` 的默认提示词仍然正确。
- The behavior around password, login, and verification still requires user action inside the controlled browser page. / 与密码、登录和验证码有关的行为仍然要求用户在受控浏览器页面内自行操作。

## 4. Commit And Push / 提交并推送

Commit the repository and push it to GitHub. / 提交并推送到 GitHub。

Recommended first tag: / 推荐首个标签：

```text
v0.1.0
```

## 5. Share Installation Path / 提供安装路径

Tell users to install from the repository path `skills/design-to-page`. / 告知使用者从仓库路径 `skills/design-to-page` 安装。

Example guidance: / 示例说明：

```text
Use $skill-installer to install from <owner>/<repo> path skills/design-to-page.
```

## 6. After Updates / 后续更新

When you update the skill: / 当你后续更新 skill 时：

- Keep the repo-facing docs bilingual if you want the public repo to remain bilingual. / 如果你希望公开仓库继续保持双语，就持续保持文档双语。
- Re-check that `openai.yaml` still matches `SKILL.md`. / 重新检查 `openai.yaml` 是否仍与 `SKILL.md` 保持一致。
- Bump the tag or release version when behavior changes materially. / 如果行为发生实质变化，更新 tag 或 release 版本。
