# Jubilee Tableau：公开修正版处理记录（2026-11-17）

## 已上传的公开求职修正版
[`Jubilee_Tableau_Portfolio_Corrected_v3.twbx`](../../Jubilee_Tableau_Portfolio_Corrected_v3.twbx)：来自用户提供的`Jubilee.twbx`，保留12张KPI工作表与1个Dashboard，内嵌脱敏CSV（1833行×49列）。

## 脱敏方式
`Customer Name`、`Name`替换为中性代号；`Customer ID`、`Salesperson ID`、`Order ID`也转换成在文件内一致的匿名ID。相同客户、员工及订单仍保留相同ID，以维护`COUNTD`等计算的唯一性口径。未公开原始行级CSV。

## 修正的指标定义
1. **Aggregate Gross Profit Margin**：`SUM([Gross_Profit]) / SUM([Revenue])`，由源CSV复算约 **70.16%**。原Dashboard的70.68%来自逐行`Gross_Profit_Margin`取平均（约70.68035%），不是总毛利/总收入。
2. **AOV / Unique Order**：`SUM([Revenue]) / COUNTD([Order ID])`，由源CSV复算约 **A$1,350.33**。原AOV A$191.29来自`SUM([Revenue]) / SUM([Customer_Order_Count])`，其分母在数据中对客户累计订单数重复求和。

## 静态检查结果
- ZIP可读；内嵌匿名CSV；相对路径`Data/Desktop/jubilee_cleaned_dashboard_data.csv`（包内内容已经匿名化）；
- 原始记录1833、匿名唯一订单1833、唯一客户298、销售人员25；
- 在Tableau XML中替换了两个公式并保留其他10张KPI；
- 未检出原学号或作者本地绝对路径。

## 重要边界和验收
作者已在Tableau Desktop中验证公开修正版可正常显示，并上传[新Dashboard截图](../../Dashboard.png)：汇总毛利率70.16%、AOV/Unique Order A$1,350.33。旧课程作业图与修正版不能混用指标。
