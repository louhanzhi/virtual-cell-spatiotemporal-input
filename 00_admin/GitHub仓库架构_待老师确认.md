# 论文资料 GitHub 仓库架构（已按蒋恒批注修订）

**项目**：虚拟细胞的时空数据 input（perspective 观点综述）
**用途**：将与本论文相关的全部材料纳入版本管理——外部文献、会议材料、团队思考与讨论、草稿、笔记、投稿等。
**状态**：以下为**已落地**的目录结构（按蒋恒批注调整后）。

---

## 一、目录结构（现行）

```
virtual-cell-spatiotemporal-input/
├── README.md                  # 仓库地图：各目录用途、论文进度、命名约定
├── .gitignore
│
├── 01_literature/             # 外部文献 —— 按论文聚合，一篇一文件夹
│   ├── 001-VirtualCell/       # 编号按 core 优先级排（001–005 core，006–013 supp）
│   │   ├── paper.pdf          #   原文（统一命名 paper.pdf）
│   │   ├── notes.md           #   本篇阅读笔记
│   │   ├── speed-reading/     #   本篇速读网页（浏览器打开 index.html）
│   │   └── README.md          #   引用信息 + 优先级 + 在文中的角色
│   ├── 002-Nicheformer/  …  013-SubcellularST-Benchmark/
│   ├── reading-list.md        # 总览：阅读清单 + 状态
│   └── references.bib         # 统一文献源（BibTeX）
│
├── 02_meetings/               # 会议材料 —— 按会议一文件夹（日期命名），原始与纪要同放
│   └── 2026-06-15_meeting_虚拟酵母FM_会议记录及ppt/
│
├── 03_discussions/            # 团队内部思考与讨论 —— 平铺，不再细分
│
├── 04_drafts/                 # 论文草稿 —— 只有 versions/，每版自带 outline
│   ├── README.md
│   └── versions/
│       └── v1/
│           ├── outline.md     # 本版骨架
│           └── draft.md       # 本版正文
│
├── 05_assets/                 # 自制图表、规格清单等素材
│
└── 00_admin/                  # 任务清单、与老师沟通记录、作业/投稿要求
```

---

## 二、按蒋恒批注做的修改

1. **`01_literature/` 改为按论文聚合**（最大改动）。
   原方案把 papers/core、papers/supplementary、notes/、speed-reading/ 横向拆开，嵌套过深、且同一篇论文的材料散在多处。
   现改为**一篇一文件夹**（`001-paper名称/`、`002-paper名称/` …），该篇的 PDF、笔记、速读、引用信息全部收在自己文件夹里。
   编号按 core 优先级排：001–005 为 core，006–013 为 supplementary；优先级写在每个文件夹的 `README.md`，不再用目录层级表达。

2. **`02_meetings/` 拍平**：去掉 transcripts/ 与 summaries/ 两个子层，改为按会议一文件夹（日期命名），原始转录与纪要同放。

3. **`03_discussions/` 拍平**：去掉 ideas/decisions/open-questions——"我们自己内部的不用分这么细"。

4. **`04_drafts/` 简化**：去掉顶层 `outline.md`；只保留 `versions/`，**每个 version 文件夹自带对应的 `outline.md` 与 `draft.md`**，骨架与草稿绑定，不会脱节。

---

## 三、命名与协作约定

- **文献文件夹**：`编号-关键词`（如 `001-VirtualCell`），内部 PDF 统一名为 `paper.pdf`。
- **会议文件夹**：日期前缀（如 `2026-06-15_meeting_xxx`）。
- **草稿版本**：`versions/v1`、`versions/v2`…，每版含自己的 `outline.md` 与 `draft.md`。
- **文献管理**：以 `references.bib`（BibTeX）为引用源，配合 Zotero 维护；引用/阅读状态在 `reading-list.md` 追踪。

## 四、仓库公开性

设为 **private**（含版权 PDF 原文）。若日后改 public，需把 PDF 与速读内联材料移出版本库或加入 `.gitignore`（见 `.gitignore` 内注释）。
