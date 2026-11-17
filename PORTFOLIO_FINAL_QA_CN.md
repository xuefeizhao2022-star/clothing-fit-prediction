# 三个核心项目与作品集网页：最终验收说明

## 当前公开可访问成果
1. **Clothing Fit**：[项目案例](projects/clothing-fit/README.md)与[带完整输出的Notebook](Clothing_Fit_Prediction_Public_%281%29.ipynb)。主指标采用Notebook同一轮结果（Accuracy 0.6770、Macro F1 0.5493），旧课程报告混淆矩阵明确标为历史版本。
2. **Australian Trade**：[案例](projects/australian-trade/README.md)、[真实贸易仪表板](D2_Trade%20Overview.png)、[真实燃料进口仪表板](D3_Fuel%20Import%20Analysis.png)、[口径说明](projects/australian-trade/ANALYSIS_NOTES_CN.md)。[公开Excel](Australian_Trade_Data_Portfolio.xlsx)、[清理过预测比较的Tableau打包工作簿](Australian_Trade_Tableau_Portfolio.twbx)与D2/D3实际截图均已上传。
3. **Jubilee KPI**：[案例](projects/financial-kpi/README.md)、[修正版Dashboard](Dashboard.png)、[数据复核](projects/financial-kpi/DATA_VALIDATION_CN.md)。[已公开脱敏修正版Tableau工作簿](Jubilee_Tableau_Portfolio_Corrected_v3.twbx)及[实际修正版Dashboard](Dashboard.png)。原始带姓名的CSV未公开。

## 数据质量与求职表述红线
- Jubilee求职版已改为按`SUM(Gross_Profit)/SUM(Revenue)`计算的毛利率70.16%；原课程Dashboard的70.68%为逐行平均，两版属于不同定义。
- Jubilee求职版AOV=SUM(Revenue)/COUNTD(Order ID)=A$1,350.33；原课程A$191.29采用累计客户订单数字段作分母，两版须明确区分。
- 课程项目不得写成企业实际委托、生产部署或A/B测试。
- Australian Trade的naïve benchmark和额外回测不得写成独立完成的个人实验。
- 已运行的Notebook不等于第三方独立复现。

## 网页交付检查
- [x] 在线GitHub Pages首页与三个重点项目入口
- [x] 搜索、岗位筛选、项目比较、中文简历与面试描述功能
- [x] 移动端CSS、键盘焦点、减少动态效果设置
- [x] 三个项目真实图表/代码入口及证据状态
- [x] 修正首页Clothing Fit历史图与新指标混用
- [x] 源材料审计、敏感字段与计算口径披露
- [ ] 浏览器实际多设备端到端测试（当前仅能静态审查HTML/CSS/JS）
- [x] Australian Trade不含旧预测比较的Excel及D2/D3打包Tableau文件已验证后上传仓库
- [x] Jubilee匿名化、修正两项公式的打包Tableau文件和实际Dashboard截图已验证后上传仓库

## 完成度解释
三个精选案例的主要公开证据均已完成上传、关联和核查；浏览器实际多设备端到端测试仍在验收清单中，不应宣称已完成自动化视觉回归。

## 已公开的源文件
- [Australian_Trade_Data_Portfolio.xlsx](Australian_Trade_Data_Portfolio.xlsx)
- [Australian_Trade_Tableau_Portfolio.twbx](Australian_Trade_Tableau_Portfolio.twbx)
- [Jubilee_Tableau_Portfolio_Corrected_v3.twbx](Jubilee_Tableau_Portfolio_Corrected_v3.twbx)

这些文件已完成静态检查，经作者使用Tableau打开确认并上传GitHub；项目主页与交互式网站均已链接至现有文件。
