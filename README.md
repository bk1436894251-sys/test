# test

这是用于学习 Git、GitHub、Pull Request（PR）和 Codex 协作流程的仓库。

## 推荐工作方式

所有修改都按下面的顺序进行：

1. 从最新的 `main` 创建一个新分支。
2. 在新分支中修改文件。
3. 查看差异并运行必要检查。
4. 创建内容清晰的小提交。
5. 推送分支并创建 Pull Request。
6. 在 GitHub 检查文件差异和自动检查结果。
7. 确认无误后合并 PR，再删除工作分支。

这样，GitHub 会保留每次提交、每个 PR、检查结果和合并记录，方便追溯每一步。

## 已启用的 GitHub 保护

- `main` 的日常修改必须通过 Pull Request。
- PR 必须通过“仓库基础检查”。
- PR 中未解决的讨论会阻止合并。
- `main` 禁止强制推送和删除，规则对仓库管理员同样生效。
- 仓库采用线性提交历史，方便阅读和追溯。

详细的新手教程见 [CODEX_GITHUB_TUTORIAL.md](CODEX_GITHUB_TUTORIAL.md)。

## 仓库结构

- `AGENTS.md`：Codex 在本仓库中应遵循的工作规则。
- `CONTRIBUTING.md`：分支、提交与 PR 规范。
- `.github/PULL_REQUEST_TEMPLATE.md`：创建 PR 时自动出现的说明模板。
- `.github/workflows/pr-check.yml`：PR 基础自动检查。
