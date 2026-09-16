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

## BK 字幕提取软件

仓库中的 `software/BKSubtitleOCR_v2_GPU便携版.zip` 是 Windows 便携版程序包。解压后，双击包内的启动程序即可运行，不需要安装 Python。

功能包括视频字幕区域预览与框选、中文/英文/自动 OCR、标准 SRT 输出、可选 TXT 输出、批量视频处理，以及在兼容环境下优先使用 GPU 加速。

下载与使用：

1. 从 GitHub 下载 `software/BKSubtitleOCR_v2_GPU便携版.zip`。
2. 使用 Windows 解压整个压缩包，不要只复制其中的 EXE。
3. 保留解压后的 `_internal` 目录，并运行启动器。

兼容性说明：Windows 10/11 64 位；支持 DirectML 的显卡会优先使用 GPU，无法使用时自动回退 CPU。不同电脑的驱动、系统组件和显卡型号可能影响速度。软件包通过 Git LFS 保存，下载时请确保 GitHub 客户端支持 LFS，或直接从仓库文件页面下载实际压缩包。

当前提交包含可运行的便携版软件和构建规格文件；PyInstaller 的 `build`、`dist` 缓存不纳入版本控制。
