# 三个核心项目与作品集网页：最终验收说明

## 当前公开可访问成果
1. **Clothing Fit**：[项目案例](projects/clothing-fit/README.md)与[带完整输出的Notebook](Clothing_Fit_Prediction_Public_(1).ipynb)。主指标采用Notebook同一轮结果（Accuracy 0.6770、Macro F1 0.5493），旧课程报告混淆矩阵明确标为历史版本。
2. **Australian Trade**：[案例](projects/australian-trade/README.md)、[真实贸易仪表板](trade_overview.png)、[真实燃料进口仪表板](fuel_imports.png)、[口径说明](projects/australian-trade/ANALYSIS_NOTES_CN.md)。收到最终Excel和Tableau打包工作簿，但源工作簿中仍有不应作为求职成果的naïve benchmark相关内容。
3. **Jubilee KPI**：[案例](projects/financial-kpi/README.md)、[真实Dashboard](jubilee_dashboard.png)、[数据复核](projects/financial-kpi/DATA_VALIDATION_CN.md)。已收到带CSV的打包工作簿。CSV包含客户和员工姓名，暂不直接公开行级数据。

## 数据质量与求职表述红线
- Jubilee打包CSV按`SUM(Gross_Profit)/SUM(Revenue)`计算的毛利率约70.16%，与原仪表板70.68%不一致；不能假装二者已一致。
- Jubilee原AOV公式使用`SUM(Customer_Order_Count)`分母；它并非标准的唯一订单数分母，简历中应称“课程工作簿定义的AOV”并说明。
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
- [ ] Australian Trade可公开源工作簿（需先安全剔除不展示的旧比较）
- [ ] Jubilee可公开的脱敏打包工作簿（需保留Tableau字段依赖并验证数值）

## 完成度解释
网站与三个案例已有可用、可核查的公开展示；**不能将上述三个未完成项描述为已通过验收**。不应为追求“100%完成”而发布含个人信息的原始工作簿或虚构一致性结论。
