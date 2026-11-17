# Tableau与Excel源文件核查（2026-11-17）

## 收到的材料
- Excel：`25966502_A3.xlsx`（尚未公开原文件，含学号）。
- Tableau打包工作簿：`25966502_A3(4).twbx`（尚未公开原文件，含学号和待排除的预测比较内容）。

## 可核实的工作簿结构
打包工作簿内有两份Excel数据副本。两份均包含以下9个工作表：`Export-dataset`、`Import-dataset`、`Export-Statistical`、`Import-Statistical`、`Export-Analytical`、`Import-Analytical`、`Dollar-Combined`、`Statistical-Combined`、`Analytical-Combined`；其中第二份额外包含`Forecast-Comparison`。

Tableau工作簿包含15张分析工作表、3个仪表板（D1/D2/D3）及一个Story（S1）。具体包括总贸易、主要类别金额/份额/同比、燃料出口/进口结构、天然气预测和预测比较等。

## 公开展示边界
- D2 Trade Overview及D3 Fuel Import Analysis已有真实截图并公开。
- 源工作簿仍含`08_Forecast Comparison`和相关预测比较内容；不能直接把整份工作簿发布为已剔除naïve benchmark的求职版本。
- 原始源文件不应直接公开学号、文件路径或不打算展示的实验；先制作衍生公开版本并验证工作簿引用关系。
- 不改写或冒充原始课程提交文件；公开案例中的指标与图表必须保持一致。

## 后续工作
验证最终Excel与打包工作簿之间的版本差异；仅在能保证Tableau依赖和数据口径正确时公开可运行的脱敏工作簿。