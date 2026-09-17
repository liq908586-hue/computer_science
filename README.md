
# Titanic - Machine Learning from Disaster

基于 Kaggle Titanic 数据集，完成从 EDA 到建模的完整数据分析流程。

## 项目背景

Titanic 是 Kaggle 最经典的入门竞赛，目标是预测乘客是否幸存。本项目旨在跑通“数据加载 → 清洗 → 特征工程 → 建模 → 提交”的完整闭环。

## 数据

- `train.csv`：891 行，12 列，含标签 `Survived`
- `test.csv`：418 行，11 列，需预测
- 缺失值：Age 177，Cabin 687，Embarked 2

## EDA 关键发现

- 整体生存率约 38%
- 女性生存率 74%，男性 19%
- 头等舱生存率 63%，二等舱 47%，三等舱 24%
- 儿童生存率明显高于成人

## 特征工程

- Age 中位数填充，Embarked 众数填充，Fare 中位数填充
- Cabin 转为二值特征 `HasCabin`
- 从 Name 提取称呼 `Title`
- 构造 `FamilySize` 和 `IsAlone`

## 模型

- 随机森林（n_estimators=100）
- 验证集准确率：0.80
- Kaggle 得分：0.74162

## 文件结构

- `data/raw/` — 原始数据
- `outputs/figures/` — EDA 图表
- `outputs/submission.csv` — Kaggle 提交文件
- `titanic.ipynb` — 完整分析代码
- `requirements.txt` — 依赖包
- `README.md` — 项目说明

## 如何运行

```bash
pip install -r requirements.txt
jupyter notebook titanic.ipynb

