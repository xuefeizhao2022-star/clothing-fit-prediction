# Jubilee：指标定义核验与公开修正版

**材料**：用户提供的 `Jubilee.twbx` 内 `Data/Desktop/jubilee_cleaned_dashboard_data.csv`。本页只公布聚合结果，不发布包含客户和员工姓名的原始行级数据。

## 数据概况
- CSV：1,833条记录、49个字段
- 唯一订单ID：1,833
- 唯一客户ID：298
- 唯一销售人员ID：25
- 包内同时包含Tableau工作簿定义与CSV，解决了单独`.twb`缺少数据连接的问题。

## 用CSV重新计算的结果

| 口径 | 计算方式 | 从CSV计算结果 | 仪表板展示 |
|---|---|---:|---:|
| Total Revenue | `SUM(Revenue)` | A$2,475,163.60 | A$2.48M |
| Gross Profit | `SUM(Gross_Profit)` | A$1,736,503.51 | A$1.74M |
| Aggregate Gross Profit Margin | `SUM(Gross_Profit)/SUM(Revenue)` | 70.16% | 修正版70.16%；原版70.68% |
| AOV / Unique Order | `SUM(Revenue)/COUNTD(Order ID)` | A$1,350.33 | 修正版A$1,350.33；原版A$191.29 |
| Avg Orders per Customer | `COUNTD(Order ID)/COUNTD(Customer ID)` | 6.15 | 6.15 |
| On-time Delivery | `AVG(On_Time_Delivery_Flag)` | 73.00% | 73.00% |
| Average Delivery Days | `AVG(Delivery_Days)` | 3.90天 | 3.90天 |
| Total Product Weight | `SUM(Total_Product_Weight_kg)` | 67,674.19 kg | 67,674 kg |
| Revenue per kg | `SUM(Revenue)/SUM(Total_Product_Weight_kg)` | A$36.57/kg | A$36.57/kg |

**问题已在求职展示版修正：** 原70.68%为逐行毛利率平均，公开版70.16%为汇总毛利率。用户已在Tableau中打开修正版，上传的[实际修正截图](../../Dashboard.png)显示70.16%及A$1,350.33，其余主要KPI也与CSV汇总及原指标四舍五入口径相符。

**AOV口径提醒：** 原课程版本的`SUM(Customer_Order_Count)`分母导致A$191.29；求职修正版改为`COUNTD(Order ID)`，得到A$1,350.33。原版数值仍是历史材料，不能与修正版图表混用。

## 证据边界
- 以上是直接读取打包CSV进行的静态计算，并非在Tableau Desktop中重新运行工作簿。
- [求职修正版TWBX](../../Jubilee_Tableau_Portfolio_Corrected_v3.twbx)包含匿名化的行级教学数据；原客户/员工姓名及原始ID未按原值公开。
- 90%准时配送是报告建议目标，不是已达成结果。
