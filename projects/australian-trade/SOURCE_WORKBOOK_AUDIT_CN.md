# Australian Trade：公开版处理记录（2026-11-17）

## 已生成的本地公开候选文件（尚未上传GitHub）
- `Australian_Trade_Data_Portfolio.xlsx`：9张Excel数据/分析工作表，剔除`Forecast-Comparison`。
- `Australian_Trade_Tableau_Portfolio.twbx`：保留13张分析工作表，以及`D2_Trade Overview`、`D3_Fuel Import Analysis`两个真实Dashboard。

## 处理过程
- 从收到的`25966502_A3(4).twbx`删除`08_Forecast Comparison`及`07_Gas Export Forecast`工作表、`D1_Gas Export Analysis`和`S1_Australian Trade Story`，以及关联的窗口/缩略图和仅供比较使用的第二个数据源。
- 改成不含学号的文件名称、数据源标题与相对路径，重新打包Excel源数据。
- 静态验证：打包文件ZIP结构完整；Tableau XML仍包含D2、D3；未检出`naive`、`benchmark`、`Forecast-Comparison`、原学号或本地绝对文件路径。

## 重要边界
已生成的文件**还没有在Tableau Desktop中重新打开验证**。在使用者确认D2/D3没有连接错误、展示数值与现有真实截图对应之前，不应宣称正式可复现；也不要上传原始带学号/额外比较的工作簿。

## 需要的验收
1. 在Tableau Desktop打开`Australian_Trade_Tableau_Portfolio.twbx`；
2. 检查D2、D3正常显示且不提示重连数据源；
3. 确认没有naïve benchmark/Forecast Comparison页面；
4. 将验证通过的公开版工作簿及Excel上传GitHub。
