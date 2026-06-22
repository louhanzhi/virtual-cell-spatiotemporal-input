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
| ☐ | [`004-stVCR/`](004-stVCR/) | stVCR — Peng, Zhou & Li (Nat Methods 2026) ⭐ | 时空动力学方法 | 与切口最近；解坐标系不对齐 + 破坏性测序痛点（OT 方法，与 Waddington-OT 同源） |
| ☐ | [`005-ST-SelectionGuide/`](005-ST-SelectionGuide/) | ST 技术选型实操指南 — Lim et al. (BMC Genomics 2025) ⭐次级 | 测量端约束 | 三难困境的弹药库：单细胞尺度只能测几百-上千基因 |

## supplementary（补充 / 选读）— 006–013

| 状态 | 文件夹 | 论文 / 年份 | 类别 | 角色 |
|---|---|---|---|---|
| ☐ | [`006-MultiScaleReview/`](006-MultiScaleReview/) | Multi-scale AIVC review (BiB 2026) | 综述 | 定位本文在综述谱系里的空隙 |
| ☐ | [`007-Preclinical/`](007-Preclinical/) | AIVC in preclinical research (npj DM 2025) | 综述 | 反衬"没人专门讲时空 input" |
| ☐ | [`008-CellPLM/`](008-CellPLM/) | CellPLM (Wen et al., 2023) | 空间感知基础模型 | 如何把坐标喂进模型（正弦位置编码） |
| ☐ | [`009-Spateo/`](009-Spateo/) | Spateo (Cell 2024) | 时空动力学方法 | 可直接抄的输入数据规格（AnnData .obsm/.X/.obs） |
| ☐ | [`010-Ultrack/`](010-Ultrack/) | **Ultrack (Nat Methods 2025)** ⟵ 替原 LivecellX 预印本 | 真·时间数据源 | 破坏性快照 vs 非破坏性活成像的二分框架（大规模时序追踪 / 发育 time-lapse） |
| ☐ | [`011-scNODE/`](011-scNODE/) | **scNODE (Bioinformatics 2024)** ⟵ 替原 CellProphet 预印本 | 时间方法 | 时间窗预测范例（VAE+neural ODE 预测未观测时间点表达） |
| ☐ | [`012-TrackMate/`](012-TrackMate/) | **TrackMate 7 (Nat Methods 2022)** ⟵ 替原 Caliban 预印本 | 真·时间数据源 | 活细胞追踪 + 谱系树重建（追踪+分割集成平台） |
| ☐ | [`013-SubcellularST-Benchmark/`](013-SubcellularST-Benchmark/) | 亚细胞 ST 平台系统基准 (Nat Commun 2025) | 测量端约束 | 各平台到底能产出什么 input 的硬数据 |

> **【2026-06-17 预印本剔除】** 正式引用不收预印本，010/011/012 三篇预印本已全部替换为已发表正刊，**文件夹已同步重命名**：
> - 010：LivecellX (bioRxiv) → **Ultrack**, Nat Methods 2025（vol 22, 2423–2436）｜目录 `010-LivecellX/` → `010-Ultrack/`。
> - 011：CellProphet (bioRxiv) → **scNODE**, Bioinformatics 2024（vol 40 Suppl 2, ISMB）｜目录 `011-CellProphet/` → `011-scNODE/`。
> - 012：Caliban (bioRxiv) → **TrackMate 7**, Nat Methods 2022（s41592-022-01507-1）｜目录 `012-Caliban/` → `012-TrackMate/`。
> - ⚠️ 各目录内旧的 `paper.pdf` / `notes.md` / `speed-reading/` 属**旧论文**、已清除；新论文的 PDF 与速读网页需另行下载/生成（见各目录 `README.md`）。

## 补充核心引用（2026-06-16 新增，仅入 `references.bib`，暂无独立文件夹）

按 perspective 三条论证线补"地基"。引用 key 见 `references.bib` 的 B 区。

| BibTeX key | 论文 / 年份 | 在文中的角色 |
|---|---|---|
| `theodoris2023geneformer` | Geneformer — Transfer learning enables predictions in network biology (Nature 2023) | 主流 input 范式来源之一：30M 解离单细胞预训练，**正是把空间/时间冲掉的那类数据** |
| `cui2024scgpt` | scGPT (Nat Methods 2024) | 同上，33M 细胞生成式基础模型；坐实"细胞被当成一管均质溶液"的批评对象 |
| `trapnell2014monocle` | Monocle / 伪时间排序 (Nat Biotechnol 2014) | 第 3 节"伪时间 ≠ 真实时钟"的源头：从静态快照**推**时间 |
| `lamanno2018rnavelocity` | RNA velocity (Nature 2018) | 第 3 节：从剪接/未剪接比例反推"未来状态"，仍是快照外推而非真实观测 |
| `marx2021methodoftheyear` | Method of the Year: spatially resolved transcriptomics (Nat Methods 2021) | 第 2 节里程碑：把"空间"确立为一个值得作 input 的维度 |
| `czi2023cellxgene` | CZ CELLxGENE Discover Census (bioRxiv 2023) | 第 5 节"时空标准化"缺口：现有社区级语料几乎全是解离数据 |

> 每篇 core 的阅读笔记在各自文件夹的 `notes.md`；速读网页在 `speed-reading/`；BibTeX 见 `references.bib`。新增的补充核心引用暂只入 `references.bib`，按需再建文件夹。
