# 论文资料 GitHub 仓库架构（提交确认稿）

**项目**：虚拟细胞的时空数据 input（perspective 观点综述）
**用途**：将与本论文相关的全部材料纳入版本管理——外部文献、会议转录、团队思考与讨论、草稿与补充阅读、笔记摘要、投稿等。
**说明**：以下为拟定的仓库目录结构，请老师审阅确认或提出调整意见。

---

## 一、目录结构

```
virtual-cell-spatiotemporal-input/
├── README.md                  # 仓库地图：各目录用途、论文进度、命名约定
├── .gitignore
│
├── 01_literature/             # 外部文献（引用的 + 补充阅读的）
│   ├── papers/                # PDF 原文
│   │   ├── core/              # 必读核心文献
│   │   └── supplementary/     # 补充与选读文献
│   ├── notes/                 # 每篇一份阅读笔记，文件名与 PDF 对应
│   ├── speed-reading/         # 速读网页（每篇一个文件夹，浏览器打开即用）
│   ├── reading-list.md        # 阅读清单 + 阅读状态追踪
│   └── references.bib         # 统一文献源（BibTeX），写作时直接引用
│
├── 02_meetings/               # 会议转录材料
│   ├── transcripts/           # 原始转录，按日期命名
│   └── summaries/             # 会议纪要 / 要点 / 决议
│
├── 03_discussions/            # 团队的综合思考与讨论（创意与产出）
│   ├── ideas/                 # 想法、论证草稿、灵感
│   ├── decisions/             # 重要决策记录（结论与理由）
│   └── open-questions/        # 待确认 / 悬而未决的问题
│
├── 04_drafts/                 # 论文草稿
│   ├── outline.md             # 论文骨架（章节结构与字数配比）
│   └── versions/              # v1, v2… 版本留存
│
├── 05_assets/                 # 自制图表、规格清单等素材
│
└── 00_admin/                  # 任务清单、与老师沟通记录、作业/投稿要求
```

---

## 二、分类边界说明

1. **"外部引用文献"与"补充阅读文献"统一存放**，都放入 `01_literature/papers/`。
   理由：某篇文献"是否最终被引用"在写作过程中会变化，不宜用目录硬性区分；
   实际引用状态通过 `references.bib` 与 `reading-list.md` 追踪。
   `papers/` 下按 **core（必读核心）** 与 **supplementary（补充选读）** 分优先级。

2. **笔记分两类**：
   - 针对单篇论文的阅读笔记 → `01_literature/notes/`（文件名与对应 PDF 一致）
   - 跨多篇的综合思考 / 自己的观点 → `03_discussions/ideas/`
   区分标准：是在转述他人，还是在产出我们自己的观点。

3. **会议材料分原始与加工**：原始转录入 `02_meetings/transcripts/`；
   人工整理的纪要、要点、决议入 `02_meetings/summaries/`。

---

## 三、命名与协作约定

- **文献文件名**：`年份_第一作者_关键词`，如 `2024_Bunne_VirtualCell.pdf`。
- **会议与草稿**：日期前缀，如 `2026-06-15_meeting.md`、`2026-06-15_draft_v2.md`。
- **文献管理**：建立 `references.bib`（BibTeX），配合 Zotero 等工具维护，
  便于协作引用与最终核对引用准确性。

## 四、请老师确认的事项

1. **仓库公开性**：建议设为 **private**。
   若设 public，则版权论文 PDF 不宜入库（存在侵权风险），
   可改为仅存"引用信息 + 链接 + 自撰笔记"。请老师指示采用哪种方式。
   → 现已按 private 创建。
2. 目录结构是否需要增删或合并层级。
3. 文献的 core / supplementary 优先级划分是否需要调整。
4. 是否需要纳入其他类型材料（如数据集、代码、图表源文件）。
