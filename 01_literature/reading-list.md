# 阅读清单 + 阅读状态

优先级：⭐ = 动笔前必读（4+1 篇核心）。状态：☐ 待读 / ◐ 在读 / ☑ 读完。

## 动笔顺序（4+1）
1. Bunne（定调）→ 2. Nicheformer（空间）→ 3. Waddington-OT + stVCR（时间）→ 4. ST 选型指南（约束）

## core（必读核心）— `papers/core/`

| 状态 | 文件 | 论文 / 年份 | 类别 | 在文中的角色 |
|---|---|---|---|---|
| ☐ | `2024_Bunne_VirtualCell.pdf` | How to Build the Virtual Cell with AI (Cell 2024) ⭐ | 愿景纲领 | 领域"宪法"，把数据生成列为 AIVC 五大优先事项；定调、必引 |
| ☐ | `2025_TejadaLapuerta_Nicheformer.pdf` | Nicheformer (Nat Methods 2025) ⭐ | 空间感知基础模型 | "空间必须当 input"的最强证据（解离数据训不出空间复杂度） |
| ☐ | `2019_Schiebinger_WaddingtonOT.pdf` | Waddington-OT (Cell 2019) ⭐ | 时间/轨迹奠基 | 从破坏性快照反推时间动力学的范式起点 |
| ☐ | `2026_stVCR.pdf` | stVCR (Nat Methods 2026) ⭐ | 时空动力学方法 | 与切口最近；解坐标系不对齐 + 破坏性测序痛点 |
| ☐ | `2025_ST-SelectionGuide.pdf` | ST 技术选型实操指南 (PMC) ⭐次级 | 测量端约束 | 三难困境的弹药库：单细胞尺度只能测几百-上千基因 |

## supplementary（补充 / 选读）— `papers/supplementary/`

| 状态 | 文件 | 论文 / 年份 | 类别 | 角色 |
|---|---|---|---|---|
| ☐ | `2026_MultiScaleReview.pdf` | Multi-scale AIVC review (BiB 2026) | 综述 | 定位本文在综述谱系里的空隙 |
| ☐ | `2025_Preclinical.pdf` | AIVC in preclinical research (npj DM 2025) | 综述 | 反衬"没人专门讲时空 input" |
| ☐ | `2023_Wen_CellPLM.pdf` | CellPLM (Wen et al., 2023) | 空间感知基础模型 | 如何把坐标喂进模型（正弦位置编码） |
| ☐ | `2024_Spateo.pdf` | Spateo (Cell 2024) | 时空动力学方法 | 可直接抄的输入数据规格（AnnData .obsm/.X/.obs） |
| ☐ | `2025_SubcellularST-Benchmark.pdf` | 亚细胞 ST 平台系统基准 (Nat Commun 2025) | 测量端约束 | 各平台到底能产出什么 input 的硬数据 |
| ☐ | `2025_LivecellX.pdf` | LivecellX (bioRxiv 2025) | 真·时间数据源 | 破坏性快照 vs 非破坏性活成像的二分框架 |
| ☐ | `2025_CellProphet.pdf` | CellProphet (bioRxiv 2025) | 时间方法 | 时间窗预测范例 |
| ☐ | `Schwartz_Caliban.pdf` | Caliban / DeepCell (Schwartz et al.) | 真·时间数据源 | 活细胞追踪 + 谱系重建（LSTM 时间上下文） |

> 每篇的逐篇阅读笔记放 `notes/`，文件名与 PDF 对应；速读网页见 `speed-reading/`。
