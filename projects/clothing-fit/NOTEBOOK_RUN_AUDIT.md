# Clothing Fit — 已运行Notebook核查记录

**材料**：用户于2026-11-17提供的 `Clothing_Fit_Prediction_Public(2).ipynb`，共70个单元格，保存了60项输出。此记录是静态核查，**不是重新执行实验**。

## 数据与划分
- 原始读取：UCSD McAuley Lab RentTheRunway公开数据 `renttherunway_final_data.json.gz`。
- 读取后记录数：192,544，字段数15。
- 模型划分：训练134,648，验证28,853，测试28,854；按类别分层；`random_state=42`。
- 最终选择：Logistic Regression，类别权重 `fit:1, small:3, large:3`，与Random Forest等候选方案比较后选定。

## 已保存测试输出（Notebook cell 56–58）
| Metric | Test |
|---|---:|
| Accuracy | 0.6770 |
| Balanced Accuracy | 0.5728 |
| Macro F1 | 0.5493 |
| Misfit Recall | 0.5196 |
| Misfit Precision | 0.4198 |
| False Alert Rate | 0.2553 |

### 本次Notebook混淆矩阵（行=真实，列=预测）
| Actual / Predicted | small | fit | large |
|---|---:|---:|---:|
| small | 1,852 | 1,882 | 128 |
| fit | 2,814 | 15,852 | 2,621 |
| large | 121 | 1,753 | 1,831 |

总计28,854；对角线19,535，Accuracy = 19,535 / 28,854 ≈ 0.6770。

### 与原始课程报告图片的差别
原报告图片的对角线为1,841、15,879、1,826（共19,546个正确预测，Accuracy ≈0.6774），与当前Notebook不同。**两者不得合并为一轮运行的结果**。原因尚未经过环境/版本差异实验确认，不能直接归因于随机波动。

## 公开前剩余工作
1. 上传脱敏Notebook并提供依赖版本及运行说明。
2. 将本次Notebook中保存的混淆矩阵和系数图作为公开案例的主图；原报告图保留明确历史版本标签，或移至附录。
3. 用独立运行核实指标、图表和数据下载链接；静态保存输出本身不等于完整复现。
4. 核查个人信息、数据授权和可能的私有路径。
