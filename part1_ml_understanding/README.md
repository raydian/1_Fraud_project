# 第一部分：机器学习学习与理解（模型体系 + 风控评估）

> 目标：不仅「会用」，更要理解不同模型的适用条件、优势劣势、可解释性与工程约束，为后续 AutoML 的模型搜索空间打基础。

---

## 目录结构

本部分按二级章节（1.1～1.4）组织，**code** 与 **knowledge** 下各有一一对应的子目录：

```
part1_ml_understanding/
├── README.md                 # 本文件
├── code/                     # 代码与示例
│   ├── 1.1_problem_modeling/  # 1.1 金融风控问题建模相关示例
│   ├── 1.2_metrics/          # 1.2 评估指标计算与可视化示例
│   ├── 1.3_time_split/       # 1.3 时间切分与防泄露示例
│   └── 1.4_models/           # 1.4 各模型使用与对比示例
├── knowledge/                # 知识点与概念说明
│   ├── 1.1_problem_modeling/ # 1.1 问题建模认知文档
│   ├── 1.2_metrics/          # 1.2 指标说明与风控视角文档
│   ├── 1.3_time_split/       # 1.3 时间切分与数据泄露文档
│   └── 1.4_models/           # 1.4 模型体系理解文档
└── docs/                     # 报告、总结等产出
```

### 文件组织约定

- **知识点**：每个概念、每个指标、每个模型**单独一个文件**，便于查阅与维护。
- **示例**：每个指标一个计算/可视化示例文件，每个模型一个使用示例文件，每个切分策略一个示例文件。
- 命名建议：`知识点或模型名.md`（knowledge）、`指标名_示例.py` 或 `模型名_示例.py`（code）。

---

## 章节与内容对照

### 1.1 金融风控问题建模认知（必须理解）

| 位置 | 建议文件/内容 |
|------|----------------|
| **knowledge/1.1_problem_modeling/** | `风控本质.md`（不平衡二分类、时间序列、分布漂移、可解释合规）、`风控数据结构.md`、`样本与标签问题.md`（标签延迟、策略变化、黑产、泄露风险） |
| **code/1.1_problem_modeling/** | 问题建模相关的小示例（如不平衡数据可视化、数据结构示例等，按需单文件） |

### 1.2 必备评估指标与风控视角（必须理解）

| 位置 | 建议文件/内容 |
|------|----------------|
| **knowledge/1.2_metrics/** | `AUC_ROC.md`、`KS.md`、`PR_AUC.md`、`Precision_Recall_F1.md`、`混淆矩阵与误杀漏放.md`、`PSI与分布漂移.md`、`线上与稳定性指标.md` |
| **code/1.2_metrics/** | 每个指标一个示例：`auc_roc_示例.py`、`ks_示例.py`、`pr_auc_示例.py`、`precision_recall_f1_示例.py`、`confusion_matrix_示例.py`、`psi_示例.py` 等 |

### 1.3 时间切分与数据泄露（风控必须掌握）

| 位置 | 建议文件/内容 |
|------|----------------|
| **knowledge/1.3_time_split/** | `为什么不能随机切分.md`、`TimeSeriesSplit与时间窗口.md`、`按用户维度切分.md`、`观察窗与表现窗.md` |
| **code/1.3_time_split/** | `time_series_split_示例.py`、`user_based_split_示例.py`、`observation_performance_window_示例.py` 等 |

### 1.4 模型体系学习与理解（重点）

| 位置 | 建议文件/内容 |
|------|----------------|
| **knowledge/1.4_models/** | `逻辑回归_LR.md`、`决策树与随机森林_RF.md`、`GBDT_XGBoost_LightGBM_CatBoost.md`、`SVM与线性模型.md`、`神经网络与深度学习.md` |
| **code/1.4_models/** | 每个模型一个示例：`lr_示例.py`、`rf_示例.py`、`xgboost_示例.py`、`lightgbm_示例.py`、`catboost_示例.py`，以及 `多模型对比实验.py`、`SHAP可解释性示例.py` 等 |

---

## 第一部分交付物（学习理解 + 初步验证）

- 风控问题建模说明（不平衡 + 时间切分 + 泄露风险）
- 多模型对比实验（LR / RF / LGBM 至少三种）
- 指标体系报告（AUC、KS、PR-AUC、阈值策略分析）
- 可解释性输出（LR 系数 + SHAP 示例）

以上产出可放在 **docs/** 中，与 code、knowledge 配合使用。
