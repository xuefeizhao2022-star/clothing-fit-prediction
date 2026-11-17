# Jubilee Tableau工作簿与报告核查（2026-11-17）

## 收到的材料
- `Jubilee.twb`：Tableau工作簿定义，包含12张KPI工作表与1个Dashboard。
- `Jubilee.pdf`：10页课程报告，含最终Dashboard截图与Balanced Scorecard分析。

## 数据连接问题
原始`.twb`使用`textscan`连接本地文件`jubilee_cleaned_dashboard_data.csv`（原路径指向作者电脑桌面）。**当前收到的文件中不包含该CSV。** 单独公开`.twb`不能保证其他人打开后成功加载数据。因此在补齐数据前，不将它包装为可复现的Tableau工作簿。

## 已核对的计算字段
- `AOV (Correct)`：`SUM([Revenue]) / SUM([Customer_Order_Count])`
- `Avg Orders per Customer`：`COUNTD([Order ID]) / COUNTD([Customer ID])`
- `Revenue per kg (Correct)`：`SUM([Revenue]) / SUM([Total_Product_Weight_kg])`

上述是工作簿中实际保存的Tableau计算表达式，**不等于已经用缺失的CSV重新计算验证**。

## 报告与Dashboard
报告将12项KPI组织为财务、客户、内部流程、学习与成长四个视角。最终截图显示营收约A$2.48m、毛利约A$1.74m、毛利率70.68%、AOV A$191.29、每客户平均订单6.15、准时配送率73%、平均配送3.90天等。90%的准时配送率是建议目标，不是实际结果。

## 下一步所需
请补充原始`jubilee_cleaned_dashboard_data.csv`（或从Tableau导出包含数据的`.twbx`），之后才能制作可移植的脱敏公开工作簿并验证KPI公式。