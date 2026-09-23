# 华为杯研究生数学建模竞赛 E 题工程化项目

## 1. 项目概述
本仓库面向第二十三届中国研究生数学建模竞赛 E 题《复杂场景下多模态情感识别的数学建模与算法设计》，完成标准化项目初始化与多模态数据工程化重构。

## 2. 目录规范与文件结构

```text
HuaweiCup-2026-Problem-E/
├── docs/                                    # 赛题说明与技术文档
│   ├── 复杂场景下多模态情感识别的数学建模与算法设计.docx
│   └── references/                          # 历年同类优秀参考作品（含说明 README）
├── data/                                    # 数据集（纯英文命名，便于代码解析）
│   ├── attachment_1_raw/                    # 附件1：原始多模态数据
│   │   ├── label_100.csv                    # 标准标签与文本（含新旧 video_id 对照）
│   │   ├── label_100.xlsx                   # 标签 Excel 表格
│   │   ├── video_id_mapping.json            # 视频 ID 双向映射表 (video_XX <-> raw_id)
│   │   ├── video_id_mapping.csv             # 视频 ID 对照表 CSV
│   │   └── videos/                          # 规范化视频目录 (video_01 ~ video_37)
│   │       └── video_XX/                    # 各样本视频切片 {clip_id}.mp4
│   ├── attachment_2_features/               # 附件2：全量特征文件与标签
│   │   ├── aligned_50.pkl                   # 对齐多模态特征 (50维/帧)
│   │   ├── unaligned_50.pkl                 # 未对齐多模态特征
│   │   └── label.xlsx                       # 全量数据集标签表
│   ├── attachment_3_missing_modalities/     # 附件3：模态缺失特征样本
│   │   ├── aligned/                         # 对齐版本 (01.pkl ~ 30.pkl)
│   │   └── unaligned/                       # 未对齐版本 (01.pkl ~ 30.pkl)
│   └── attachment_4_explainability/         # 附件4：可解释专项特征与视频
│       ├── aligned/                         # 对齐特征 (01.pkl ~ 20.pkl) 及 videos/
│       └── unaligned/                       # 未对齐特征 (01.pkl ~ 20.pkl) 及 videos/
├── notebooks/                               # EDA 与实验原型
├── src/                                     # 核心源码包
│   ├── __init__.py
│   ├── data/                                # 数据加载、特征读取与缺失补全模块
│   │   ├── __init__.py
│   │   └── loader.py                        # 标准数据读取接口
│   ├── models/                              # 特征融合与深度学习模型定义
│   │   └── __init__.py
│   └── utils/                               # 评测指标与工具函数
│       └── __init__.py
├── results/                                 # 实验图表、模型权重与预测输出
├── .gitignore                               # Git 忽略配置
├── requirements.txt                         # Python 环境依赖
└── README.md                                # 项目文档
```

## 3. 数据集与代码读取规范

### 3.1 附件1 (原始样本)
- 规范化视频路径：`data/attachment_1_raw/videos/video_{01..37}/{clip_id}.mp4`
- 标签与文本表：`data/attachment_1_raw/label_100.csv`（包含 `video_id`、`clip_id`、`text`、`label`、`annotation` 及 `raw_video_id`）
- 映射对照表：`data/attachment_1_raw/video_id_mapping.json` (或 `.csv`)

### 3.2 附件2 (基础特征)
- 对齐特征：`data/attachment_2_features/aligned_50.pkl`
- 未对齐特征：`data/attachment_2_features/unaligned_50.pkl`
- 标签文件：`data/attachment_2_features/label.xlsx`

### 3.3 附件3 (模态缺失样本)
- 文件已按双位数编号归一化（`01.pkl` 至 `30.pkl`）：
  - 对齐特征：`data/attachment_3_missing_modalities/aligned/{idx:02d}.pkl`
  - 未对齐特征：`data/attachment_3_missing_modalities/unaligned/{idx:02d}.pkl`

### 3.4 附件4 (可解释专项样本)
- 特征文件已归一化（`01.pkl` 至 `20.pkl`）：
  - 对齐特征：`data/attachment_4_explainability/aligned/{idx:02d}.pkl`
  - 未对齐特征：`data/attachment_4_explainability/unaligned/{idx:02d}.pkl`
- 专项视频：`data/attachment_4_explainability/aligned/videos/{idx:02d}.mp4`
