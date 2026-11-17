# Clothing Fit Risk Prediction | 服装尺码适配风险预测

> UTS Master of Business Analytics · Advanced Data Analytics Algorithms · Individual coursework project

## 业务问题
在线服装租赁场景中，用户在租赁前可能选到偏小或偏大的尺码。本项目使用公开 RentTheRunway 数据，预测 `small`、`fit`、`large` 三类尺码反馈，并讨论将 `small` 和 `large` 作为错码预警信号时的业务取舍。

**项目性质：** 个人课程机器学习项目和推理演示，不是已上线的商业推荐系统。

## 数据和特征
- 数据来源：UCSD McAuley Lab / RentTheRunway 数据集。
- 清洗后按类别分层划分为 70% 训练、15% 验证、15% 测试。
- Notebook保存的样本量：训练 134,648；验证 28,853；测试 28,854。
- 初始训练使用8项客户和租赁相关特征，包括尺码、年龄、体重、身高、胸围、体型、服装类别和租赁用途；后续引入产品标识，形成9特征版本。
- 评分和评论等租赁后信息未进入训练，以避免在租赁前预测时使用未来信息。
- 数值特征采用训练集统计量填补并标准化；类别特征处理缺失后独热编码。

## 建模流程
1. 检查重复、缺失和异常值，建立可重复的预处理流程。
2. 建立多数类基线、标准 Logistic Regression 和类别加权 Logistic Regression。
3. 增加产品标识，比较改进后的 Logistic Regression 与 Random Forest。
4. 在验证集比较不同类别权重，兼顾 Macro F1、错码召回率和误报率。
5. 固定最终权重 `fit:1, small:3, large:3`，合并训练与验证集重新拟合，仅在最终测试集评估一次。

## 最终测试集结果

| 指标 | 数值 |
|---|---:|
| Accuracy | 0.6770 |
| Balanced Accuracy | 0.5728 |
| Macro F1 | 0.5493 |
| Misfit Recall | 0.5196 |
| Misfit Precision | 0.4198 |
| False Alert Rate | 0.2553 |

以上取自2026-11-17收到的运行完成Notebook **Section 9 / cells 56–58 的保存输出**，测试集样本量为28,854。其Section 13与此处一致；不同数值（0.6774 / 0.5718 / 0.5489）来自原始课程报告截图版本，不是本次Notebook的Section 13。

### 为什么不直接选择最高准确率？
多数类基线在验证集的 Accuracy 为 0.7377，但其 Balanced Accuracy 只有 0.3333，且不能识别错码风险。最终模型的准确率较低，但更符合“识别不合适尺码”的业务目标。模型的误报率仍约25.53%，因此结果更适合作为研究性预警演示，而不是直接用于生产。

## 个人贡献
作为个人课程项目，完成数据质量检查、特征选择、预处理流水线、候选模型训练与比较、类别权重调整、测试评估和结果解释。

## 局限与下一步
- 加入产品标识后，现有测试主要反映训练期间已有产品的情况；新商品的泛化效果尚未验证。
- 数据来自历史租赁记录，不应直接推断对所有服装电商场景有效。
- 尚未完成生产部署、真实用户实验或线上A/B测试。
- 下一步：补充依赖锁定与在独立环境中复核运行；公开Notebook已包含同一轮运行的模型指标和图表。

## 作品集
[中文交互式作品集](https://xuefeizhao2022-star.github.io/clothing-fit-prediction/)

## 数据来源
Misra, R., Wan, M., & McAuley, J. (2018). *Decomposing fit semantics for product size recommendation in metric spaces*. RecSys 2018. https://doi.org/10.1145/3240323.3240398


---
## 公开代码与运行结果

**[查看已运行的完整 Notebook（代码、模型评估、混淆矩阵和系数图）](../../Clothing_Fit_Prediction_Public_(1).ipynb)**

此公开文件由项目作者在 Google Colab 运行并保存输出；已静态检查：70个单元格、60项输出、8张内嵌图表、无保存的Python报错，未检出此前学号。该检查不等于在独立环境中重新执行实验。

**本页的模型指标与混淆矩阵均以公开Notebook的同一次运行输出为准。**

| Actual / Predicted | small | fit | large |
|---|---:|---:|---:|
| small | 1,852 | 1,882 | 128 |
| fit | 2,814 | 15,852 | 2,621 |
| large | 121 | 1,753 | 1,831 |

测试集28,854条；对角线19,535条；Accuracy约0.6770。完整原始图表请直接打开上述Notebook的Section 9与Section 11。

### 原始课程报告图（历史版本，不用于上述指标）

原报告另有一张混淆矩阵（对角线1,841、15,879、1,826，Accuracy约0.6774）和系数图。它们来自不同保存版本，故不在本页作为当前模型的主图展示；原始文件仍保留于仓库供核查：[原报告混淆矩阵](../../clothing_confusion_matrix.png) · [原报告系数图](../../clothing_coefficients.png)。

[查看运行核查与版本差异](NOTEBOOK_RUN_AUDIT.md) · [查看英文模型复现说明](MODEL_RESULTS_AND_REPRODUCIBILITY.md)
