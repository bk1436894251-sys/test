# Codex 连接 GitHub：新手操作教程

## 一、先理解四个核心概念

- **仓库（repository）**：项目及其全部修改历史。
- **分支（branch）**：为一次修改建立的独立工作线，不直接影响正式版本。
- **提交（commit）**：一次带说明的历史快照。
- **Pull Request（PR）**：把分支修改提交给 `main` 前的对比、检查和确认页面。

推荐流程是：

```text
main → 新分支 → 修改 → commit → push → PR → 检查 → merge
```

## 二、本机仓库位置

本项目已克隆到：

```text
C:\Users\Administrator\Documents\Codex\2026-09-11\ce\test
```

在 Codex 中把这个文件夹保存为项目。以后从这个项目中新建任务，Codex 就能读取 `AGENTS.md` 并按仓库规范工作。

## 三、首次连接 GitHub

首次推送时，Windows 的 Git Credential Manager 通常会打开 GitHub 登录授权页。请由你本人完成登录和授权，不要把密码、验证码或访问令牌发给 Codex。

授权完成后，凭据由系统凭据管理器保存。以后正常的 `git fetch`、`git pull` 和 `git push` 通常不需要重复登录。

## 四、每次修改的标准流程

### 1. 同步主分支

```powershell
git switch main
git pull --ff-only origin main
```

### 2. 创建工作分支

```powershell
git switch -c docs/update-readme
```

把 `docs/update-readme` 换成这次工作的名称。不要在 `main` 上直接修改。

### 3. 查看当前状态

```powershell
git status
```

### 4. 查看修改内容

```powershell
git diff
git diff --check
```

### 5. 暂存并提交

```powershell
git add README.md
git diff --staged
git commit -m "docs: update readme"
```

不确定时不要使用 `git add .`，逐个写出文件名更容易避免误提交。

### 6. 推送工作分支

```powershell
git push -u origin docs/update-readme
```

### 7. 创建 PR

推送完成后打开 GitHub 仓库，点击 **Compare & pull request**。确认：

- base 是 `main`
- compare 是你的工作分支
- Files changed 中只有本次需要的修改
- PR 模板中的检查项符合真实情况

然后创建 PR。自动检查通过、文件差异确认无误后，再点击 **Merge pull request**。

### 8. 合并后同步本机

```powershell
git switch main
git pull --ff-only origin main
git branch -d docs/update-readme
```

远程分支可以在 PR 合并页面点击 **Delete branch** 删除。

## 五、怎样让 Codex 帮你工作

可以直接这样说：

> 在这个仓库新建分支 `docs/update-guide`，修改教程，检查差异并提交。先不要推送。

确认本地修改后，再说：

> 把当前分支推送到 GitHub，并帮我准备 PR 标题和说明。

如果希望它完整处理，可以说：

> 为这个需求创建独立分支，修改、验证、提交并创建 PR，不要合并。

PR 合并属于影响正式版本的操作。建议查看 GitHub 的 Files changed 和 Checks 后，再明确要求合并。

## 六、如何查看每一步记录

- GitHub 仓库首页的 **commits**：查看每次提交。
- PR 页面的 **Conversation**：查看说明和讨论。
- PR 页面的 **Commits**：查看该 PR 包含的提交。
- PR 页面的 **Checks**：查看自动检查结果。
- PR 页面的 **Files changed**：逐行查看实际改动。
- 本机运行 `git log --oneline --graph --decorate --all`：查看分支和提交历史。

## 七、重要安全规则

- 不要提交 API Key、密码、验证码、Cookie、访问令牌和私人文件。
- `.env` 应放进 `.gitignore`，只提交 `.env.example` 示例文件。
- 不要随便使用 `git push --force`、`git reset --hard` 或删除远程分支。
- 推送前一定查看 `git status` 和 `git diff --staged`。
- GitHub 显示秘密泄漏警告时，先撤销密钥，再处理 Git 历史；只删除文件通常不够。

## 八、仓库设置建议

初始文件推送成功后，可在 GitHub 的 **Settings → Branches** 或 **Settings → Rules → Rulesets** 中保护 `main`：

1. 要求修改必须通过 Pull Request。
2. 要求自动检查通过后才能合并。
3. 禁止强制推送。
4. 禁止删除 `main`。

只有你一个人使用仓库时，可不强制审批人数，否则自己的 PR 可能无法自行合并。建议仍然要求 PR 和自动检查，以保留完整轨迹。
