# Jubilee Tableau打包工作簿核查（2026-11-17）

## 文件状态
用户已补充`Jubilee.twbx`。本地实际解包确认包含：
- `Jubilee.twb`（Tableau工作簿，12张KPI工作表、1个Dashboard）
- `Data/Desktop/jubilee_cleaned_dashboard_data.csv`（1833行、49列，1834行含表头）

**此前“缺少CSV”的问题已经解决。** 打包工作簿的`textscan`连接指向包内相对路径`Data/Desktop`，不再依赖作者桌面的绝对路径。

## 隐私与发布限制
CSV中含`Customer Name`、`Name`（员工姓名）、`Customer ID`、`Salesperson ID`等字段。即使这是课程数据，也不能在未经确认其合成性质/授权及脱敏前直接把整份`.twbx`发布到公开GitHub。当前只公开已经核对的Dashboard截图和案例分析。

## 已检查的结构
- 12张KPI工作表与1个Dashboard
- CSV无缺失单元格（1833行×49列）
- 数据连接指向打包文件内的CSV
- 这是一项**静态结构检查**，不是在Tableau Desktop中重新打开验证全部计算值

## 业务指标
- 报告与已发布的真实Dashboard截图包含营收约A$2.48m、毛利约A$1.74m、毛利率70.68%、AOV A$191.29、每客户平均订单6.15、准时交付率73%、平均交付3.90天等。
- 90%的准时交付率是提出的目标，非实际已达到水平。

## 下一步
制作脱敏的可公开数据版本，检查字段依赖和计算字段后，验证Dashboard与原始报告数值一致，再决定是否公开打包工作簿。
