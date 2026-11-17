# Australian Trade：公开版处理记录（2026-11-17）

## 已上传的公开求职版本
- `Australian_Trade_Data_Portfolio.xlsx`：9张Excel数据/分析工作表，剔除`Forecast-Comparison`。
- `Australian_Trade_Tableau_Portfolio.twbx`：保留13张分析工作表，以及`D2_Trade Overview`、`D3_Fuel Import Analysis`两个真实Dashboard。

## 处理过程
- 从收到的`25966502_A3(4).twbx`删除`08_Forecast Comparison`及`07_Gas Export Forecast`工作表、`D1_Gas Export Analysis`和`S1_Australian Trade Story`，以及关联的窗口/缩略图和仅供比较使用的第二个数据源。
- 改成不含学号的文件名称、数据源标题与相对路径，重新打包Excel源数据。
- 静态验证：打包文件ZIP结构完整；Tableau XML仍包含D2、D3；未检出`naive`、`benchmark`、`Forecast-Comparison`、原学号或本地绝对文件路径。

## 重要边界
作者已在Tableau Desktop中打开确认D2/D3正常显示；公开版文件已经上传GitHub。仍不宣称第三方独立复现或对原始统计来源完成审计。

## 公开文件
- [Excel数据与计算表](../../Australian_Trade_Data_Portfolio.xlsx)
- [Tableau打包工作簿](../../Australian_Trade_Tableau_Portfolio.twbx)
- [D2导出图](../../D2_Trade%20Overview.png) · [D3导出图](../../D3_Fuel%20Import%20Analysis.png)
