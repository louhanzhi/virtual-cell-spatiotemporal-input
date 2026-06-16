# 阅读清单 + 阅读状态

文献按论文聚合，**一篇一文件夹**（`编号-关键词/`），编号按 core 优先级排。每个文件夹内有 `paper.pdf` / `notes.md` / `speed-reading/` / `README.md`。

优先级：⭐ = 动笔前必读（4+1 篇核心）。状态：☐ 待读 / ◐ 在读 / ☑ 读完。

## 动笔顺序（4+1）
1. 001 Bunne（定调）→ 2. 002 Nicheformer（空间）→ 3. 003 Waddington-OT + 004 stVCR（时间）→ 4. 005 ST 选型指南（约束）

## core（必读核心）— 001–005

| 状态 | 文件夹 | 论文 / 年份 | 类别 | 在文中的角色 |
|---|---|---|---|---|
| ☐ | [`001-VirtualCell/`](001-VirtualCell/) | How to Build the Virtual Cell with AI (Cell 2024) ⭐ | 愿景纲领 | 领域"宪法"，把数据生成列为 AIVC 五大优先事项；定调、必引 |
| ☐ | [`002-Nicheformer/`](002-Nicheformer/) | Nicheformer (Nat Methods 2025) ⭐ | 空间感知基础模型 | "空间必须当 input"的最强证据（解离数据训不出空间复杂度） |
| ☐ | [`003-WaddingtonOT/`](003-WaddingtonOT/) | Waddington-OT (Cell 2019) ⭐ | 时间/轨迹奠基 | 从破坏性快照反推时间动力学的范式起点 |
| ☐ | [`004-stVCR/`](004-stVCR/) | stVCR (Nat Methods 2026) ⭐ | 时空动力学方法 | 与切口最近；解坐标系不对齐 + 破坏性测序痛点 |
| ☐ | [`005-ST-SelectionGuide/`](005-ST-SelectionGuide/) | ST 技术选型实操指南 (PMC) ⭐次级 | 测量端约束 | 三难困境的弹药库：单细胞尺度只能测几百-上千基因 |

## supplementary（补充 / 选读）— 006–013

| 状态 | 文件夹 | 论文 / 年份 | 类别 | 角色 |
|---|---|---|---|---|
| ☐ | [`006-MultiScaleReview/`](006-MultiScaleReview/) | Multi-scale AIVC review (BiB 2026) | 综述 | 定位本文在综述谱系里的空隙 |
| ☐ | [`007-Preclinical/`](007-Preclinical/) | AIVC in preclinical research (npj DM 2025) | 综述 | 反衬"没人专门讲时空 input" |
| ☐ | [`008-CellPLM/`](008-CellPLM/) | CellPLM (Wen et al., 2023) | 空间感知基础模型 | 如何把坐标喂进模型（正弦位置编码） |
| ☐ | [`009-Spateo/`](009-Spateo/) | Spateo (Cell 2024) | 时空动力学方法 | 可直接抄的输入数据规格（AnnData .obsm/.X/.obs） |
| ☐ | [`010-LivecellX/`](010-LivecellX/) | LivecellX (bioRxiv 2025) | 真·时间数据源 | 破坏性快照 vs 非破坏性活成像的二分框架 |
| ☐ | [`011-CellProphet/`](011-CellProphet/) | CellProphet (bioRxiv 2025) | 时间方法 | 时间窗预测范例 |
| ☐ | [`012-Caliban/`](012-Caliban/) | Caliban / DeepCell (Schwartz et al.) | 真·时间数据源 | 活细胞追踪 + 谱系重建（LSTM 时间上下文） |
| ☐ | [`013-SubcellularST-Benchmark/`](013-SubcellularST-Benchmark/) | 亚细胞 ST 平台系统基准 (Nat Commun 2025) | 测量端约束 | 各平台到底能产出什么 input 的硬数据 |

> 每篇的阅读笔记在各自文件夹的 `notes.md`；速读网页在 `speed-reading/`；BibTeX 见 `references.bib`。
