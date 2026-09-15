# 贡献与版本记录规范

## 分支命名

- `feat/简短名称`：增加功能
- `fix/简短名称`：修复问题
- `docs/简短名称`：修改说明文档
- `chore/简短名称`：配置、整理等维护工作

例如：`docs/add-install-guide`。

## 提交信息

使用 `类型: 简短说明`：

- `feat: add user login`
- `fix: handle empty input`
- `docs: update beginner tutorial`
- `chore: configure pull request checks`

一个提交尽量只表达一件事情。提交前使用 `git diff --check` 检查空白错误，并查看 `git diff --staged` 确认将被记录的内容。

## Pull Request

PR 应写清楚：

1. 修改了什么。
2. 为什么修改。
3. 如何验证。
4. 是否存在风险或后续工作。

不要把密钥、验证码、密码、私人文件或 `.env` 文件提交到仓库。即使之后删除，秘密内容仍可能保留在 Git 历史中。
