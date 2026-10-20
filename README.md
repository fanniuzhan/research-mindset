# Research Mindset

用户自建的三个科研 skills：

- `skills/google-ml-research/`
- `skills/research-workflow/`
- `skills/research-data-thinking/`

## 版本管理

research-workflow 的每个已找到快照都按顺序单独提交到同一路径，历史通过 Git commit 查看。后续每个实际保存的版本也单独提交。`snapshot-1/2/3` 是本次导入编号，并非原有发布版本号。

导入日期为 2026-10-20；提交日期反映导入时间，不代表最初编写时间。前两版来自整合前保留的工作区和安装目录；当前快照包含课堂科研方法与实验设计补充。其他两个 skill 各找到一个当前版本。未找到的历史不作推测。

`manifest.json` 记录该提交下的实际文件及 SHA-256。安装时复制所需 skill 的完整目录，并按其要求准备依赖；本仓库不会自动同步本机安装目录。

## Research-workflow 提交索引

| 快照 | 内容 | Commit |
| --- | --- | --- |
| snapshot-1 | 整合前工作区快照 | [`a459f73`](https://github.com/fanniuzhan/research-mindset/commit/a459f730ffa4c0cf76e83ad4f104a5467f969542) |
| snapshot-2 | 整合前安装快照 | [`eeb72d7`](https://github.com/fanniuzhan/research-mindset/commit/eeb72d78798e9a54332b16d496da9f6b753671ff) |
| snapshot-3 | 课堂方法与实验设计整合后的当前快照 | [`9edf87d`](https://github.com/fanniuzhan/research-mindset/commit/9edf87d2b9d7f94bb18e6d1133bf10edcd65a251) |

查看某版：`git show <commit>:skills/research-workflow/SKILL.md`。
