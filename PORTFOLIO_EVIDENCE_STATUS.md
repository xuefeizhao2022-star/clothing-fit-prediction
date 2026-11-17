# 作品集材料状态（更新于2026-11-17）

本表区分**已公开的真实证据**与**尚未公开的可选源文件**。课程项目不是商业部署成果。

| 项目 | 已公开、可查看 | 可选后续完善 |
|---|---|---|
| Clothing Fit Risk Prediction | [运行完成Notebook](Clothing_Fit_Prediction_Public_(1).ipynb)（70个单元格、60项输出、8张内嵌图表）；[中文案例](projects/clothing-fit/README.md)；[运行结果核查](projects/clothing-fit/NOTEBOOK_RUN_AUDIT.md) | 在独立环境执行完整复现；固定依赖版本；原始课程报告仅作历史版本对照 |
| Australian Trade & Gas Export Outlook | [中文案例](projects/australian-trade/README.md)、[真实Tableau贸易总览](trade_overview.png)、[燃料进口分析](fuel_imports.png)、[数据口径说明](projects/australian-trade/ANALYSIS_NOTES_CN.md) | 核对最终Excel与Tableau工作簿后再考虑公开；不要把AI-assisted naïve benchmark / retrospective check列为已完成的个人实验 |
| Jubilee Superstores KPI Dashboard | [中文案例](projects/financial-kpi/README.md)、[真实12项KPI Dashboard](jubilee_dashboard.png)、[业务洞察](projects/financial-kpi/BUSINESS_INSIGHTS_CN.md) | 可补充经脱敏的Tableau工作簿或计算字段；目前不声称已上传 |

## Clothing Fit版本区分
- 当前公开Notebook的测试结果：Accuracy 0.6770、Balanced Accuracy 0.5728、Macro F1 0.5493；其内嵌混淆矩阵与指标对应同一轮保存输出。
- 仓库历史报告图 [clothing_confusion_matrix.png](clothing_confusion_matrix.png) 对应旧版本Accuracy约0.6774，**不能用来说明当前Notebook的0.6770**。
- 作者已在Colab运行并保存结果；本次静态核查没有发现保存的Python报错或此前学号，**并非第三方独立重跑**。

## 真实性与隐私边界
- 课程作业与实际商业项目分开表述。
- 未上传的工作簿、报告和源文件不提供虚构下载链接。
- 不公开包含学号、账户凭据或私人Cookie的原始文件。
- 不将规划目标、模型演示或预测当成真实企业运营结果。
