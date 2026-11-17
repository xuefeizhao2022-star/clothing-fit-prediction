# Jubilee：打包数据的指标复核

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
| Gross Profit Margin | `SUM(Gross_Profit)/SUM(Revenue)` | 70.16% | 70.68% |
| AOV (工作簿字段定义) | `SUM(Revenue)/SUM(Customer_Order_Count)` | A$191.29 | A$191.29 |
| Avg Orders per Customer | `COUNTD(Order ID)/COUNTD(Customer ID)` | 6.15 | 6.15 |
| On-time Delivery | `AVG(On_Time_Delivery_Flag)` | 73.00% | 73.00% |
| Average Delivery Days | `AVG(Delivery_Days)` | 3.90天 | 3.90天 |
| Total Product Weight | `SUM(Total_Product_Weight_kg)` | 67,674.19 kg | 67,674 kg |
| Revenue per kg | `SUM(Revenue)/SUM(Total_Product_Weight_kg)` | A$36.57/kg | A$36.57/kg |

**重要发现：** 按CSV聚合的毛利率约为70.16%，与原Dashboard的70.68%有差异，必须检查原Tableau计算字段和聚合方式后才能说完全一致。其余列出的指标与仪表板展示值在四舍五入后吻合。

**AOV口径提醒：** 工作簿中AOV公式使用`SUM(Customer_Order_Count)`作为分母，得到A$191.29；这不等同于通常定义的`SUM(Revenue)/COUNTD(Order ID)`，后者按此CSV约为A$1,350.33。求职展示时必须如实说明原作业的分母定义，不能直接称为标准“每订单平均收入”而不作解释。

## 证据边界
- 以上是直接读取打包CSV进行的静态计算，并非在Tableau Desktop中重新运行工作簿。
- 客户、员工姓名与ID等行级字段未公开。
- 90%准时配送是报告建议目标，不是已达成结果。
