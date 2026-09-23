# 参考作品库（docs/references/）

面向 2026 年第二十三届华为杯 E 题《复杂场景下多模态情感识别的数学建模与算法设计》整理的参考作品。
每类仅收录最值得推荐的作品，命名规范统一为 `{年份}_{来源/会议}_{主题}_{类型或编号}.pdf`。
对每篇作品均标注**是否存在开源代码仓库**（✅ 有 / ❌ 无）。

检索与整理日期：2026-09-23。

## 一、学术会议与期刊论文（4 篇，均已下载）

| 文件 | 论文 / 出处 | 开源代码仓库 | 借鉴点 |
|---|---|---|---|
| `2019_ACL_MulT_未对齐多模态Transformer融合.pdf` | MulT: Multimodal Transformer for Unaligned Multimodal Language Sequences（ACL 2019） | ✅ 官方：[yaohungt/Multimodal-Transformer](https://github.com/yaohungt/Multimodal-Transformer)（支持 CMU-MOSEI，与本题附件格式同源） | **第 2 问核心**：未对齐序列（`unaligned_50.pkl`）双向跨模态 Transformer 融合；注意力图用于**第 4 问** |
| `2020_ACMMM_MISA_模态不变与特有表征分解.pdf` | MISA: Modality-Invariant and -Specific Representations（ACM MM 2020） | ✅ 官方：[declare-lab/MISA](https://github.com/declare-lab/MISA) | 模态不变/特有子空间分解与分布对齐，对缺失、噪声更鲁棒（**第 2、3 问**） |
| `2021_AAAI_Self-MM_自监督多任务多模态情感分析.pdf` | Self-MM: Self-Supervised Multi-task Learning for Multimodal Sentiment Analysis（AAAI 2021） | ✅ 官方：[thuiar/MMSA](https://github.com/thuiar/MMSA)（统一框架含 Self-MM、TFN 等基线；独立仓库 thuiar/Self-MM） | 单模态伪标签自监督使单模态子网络独立可用，是**第 3 问模态缺失**的首选基线；评测指标体系（Acc-2/Acc-7/F1/MAE/Corr）可照搬 |
| `2025_计算机学报_AUMDF_知识蒸馏应对不确定模态缺失_期刊论文.pdf` | 《基于知识蒸馏与动态调整机制的多模态情感分析模型》（AUMDF），《计算机学报》2025 年第 48 卷第 8 期，王楠等（吉林财经大学/吉林大学） | ❌ 作者未公开代码（论文写明对比实验基于他人公开代码库复现）；同方向开源可参考 [WarmCongee/SDUMC](https://github.com/WarmCongee/SDUMC)（ICASSP 2025）、[YetZzzzzz/CMAD](https://github.com/YetZzzzzz/CMAD) | **与第 3 问（模态缺失）完全对口**的中文权威期刊方案：模态随机缺失训练策略、多模态掩码 Transformer、动态权重调整、对比/相似性双路知识蒸馏；其实验设置与消融写法可直接借鉴 |

## 二、数学建模比赛作品（7 份，均已下载）

| 文件 | 作品 / 比赛 | 开源代码仓库 | 借鉴点 |
|---|---|---|---|
| `2020_华为杯C题_脑电信号分析与判别_参赛论文_编号C20102860127.pdf` | 第十七届华为杯 C 题《面向康复工程的脑电信号分析和判别模型》（东南大学队） | ❌ 本队无公开仓库；题目与第三方复现代码见 [Allenhong0218/2020_huawei_C](https://github.com/Allenhong0218/2020_huawei_C)（非本队作者） | **第 1 问范式**：原始信号→滤波→时频特征（FFT/小波/CSP）→降维→分类；小样本不平衡处理 |
| `2020_华为杯E题_大雾能见度估计与预测_参赛论文_编号E20102690219.pdf` | 第十七届华为杯 E 题《大雾天气下的能见度估计与预测》（华东师范大学队） | ❌ 无公开仓库 | 数模中少见的**图像特征+数值数据双源融合**（暗通道/透射率特征+回归），融合策略可迁移至**第 1、2 问** |
| `2021_MathorCup_C题_细粒度情感分析与游客目的地印象_参赛论文.pdf` | 第十一届 MathorCup C 题《游客目的地印象分析》（2021） | ❌ 无公开仓库（所用 RAM 模型基于公开 AI Challenger 2018 数据集，可自行复现） | **文本模态情感分析**直接对标：细粒度情感模型+迁移学习做评论情感极性提取，TF-IDF 词云/无效文本检测对**第 1 问文本特征**有参考价值 |
| `2021_美赛MCM_D题_现代音乐风格演化_Finalist_编号2104738.pdf` | 2021 MCM/ICM D 题《From Boogie to Indie: The Evolution of Modern Music》（Finalist） | ❌ 无公开仓库 | 多源数据（音频/歌词/榜单）特征提取+时间演化建模；美赛 O/F 奖级别的**摘要与结构写作范本** |
| `2023_华为杯E题_出血性脑卒中智能诊疗_参赛论文1_集成静态与时序模型.pdf` | 第二十届华为杯 E 题《出血性脑卒中临床智能诊疗建模》 | ✅ 作者开源：[ydchen0806/23yansaiE](https://github.com/ydchen0806/23yansaiE)（论文 PDF+LaTeX 源码+代码+预处理 notebook 全套） | 多源特征工程+静态/时序模型集成；**数模论文结构、图表规范、实验表格组织**的直接模板 |
| `2023_华为杯E题_出血性脑卒中智能诊疗_参赛论文2_多模态时空特征_编号23100650012.pdf` | 同上题（另一参赛队，多模态时空特征融合+注意力图网络方案） | ❌ 未找到公开仓库 | 同为"多模态"赛题的获奖思路：多模态特征融合+注意力图网络，注意力可视化对应**第 4 问** |
| `2025_华为杯E题_高速列车轴承故障诊断_参赛论文_编号E25104860052.pdf` | 第二十二届华为杯 E 题《高速列车轴承智能故障诊断》 | ✅ 作者开源：[wxzher/2025-HuaweiCup-E](https://github.com/wxzher/2025-HuaweiCup-E)（paper/ 目录即本论文） | 信号特征提取+端到端深度诊断，与本题第 1、2 问同构；消融实验组织最具时效性 |

## 三、推荐但无法公开下载的作品（3 项）

| 作品 | 比赛类别 | 不可下载原因 | 替代资源（代码仓库情况） |
|---|---|---|---|
| 2024 年第二十一届 C 题《数据驱动下磁性元件的磁芯损耗建模》一等奖论文 | 研究生数模（华为杯） | 官方优秀论文未公开散布；GitHub 检索仅有参赛代码仓库无论文 | 参赛代码：[Tereaslle/2024-CPGMCM](https://github.com/Tereaslle/2024-CPGMCM)（❌ 无论文）。该题一等奖普遍含 SHAP 可解释性章节，建议经研创网"优秀论文"专区或《数学建模及其应用》期刊获取 |
| 2023 年第二十届 F 题《强对流降水临近预报》获奖论文 | 研究生数模（华为杯） | 一等奖论文未公开 | 相关深度学习实现：[growvv/STFormer](https://github.com/growvv/STFormer)、[uniquezhiyuan/ImagesSequencesPredictions](https://github.com/uniquezhiyuan/ImagesSequencesPredictions)（均非赛题论文仓库） |
| 2025 年美赛 MCM C 题《奥运奖牌榜模型》O 奖论文 | 美赛 MCM/ICM | COMAP 官网只公布获奖名单，O 奖全文仅刊于 UMAP Journal（付费，已核实） | 非官方解题代码：[jtchen-ai/COMAP-MCM-ICM-2025](https://github.com/jtchen-ai/COMAP-MCM-ICM-2025)（❌ 非 O 奖论文） |

## 四、与本题四问的对应关系（速查）

- **问题 1（特征提取）**：2025 华为杯 E 题（信号+深度特征）、2020 华为杯 C 题（EEG 时频特征）、2020 华为杯 E 题（图像特征）、2021 MathorCup（文本情感特征）
- **问题 2（多模态融合建模）**：MulT（未对齐跨模态注意力融合）、MISA（模态不变/特有分解）、2023 华为杯 E 题论文 2（多模态时空特征融合）
- **问题 3（模态缺失）**：AUMDF（《计算机学报》2025，与本问完全对口：缺失训练策略+蒸馏）、Self-MM（单模态自监督，缺失鲁棒）、MISA（分布对齐提升鲁棒性）；Self-MM/MISA 代码开源，可直接对接附件二 MOSEI 格式
- **问题 4（可解释性）**：MulT / 2023 华为杯 E 题论文 2（注意力可视化）、2023 华为杯 E 题论文 1（可解释叙事写作）；SHAP 写法参考 2024 C 题（见第三节获取途径）
