# 折线图｜Line chart

> 研究对象：RAWGraphs Charts v1.1.0，`src/linechart`；**源码原生分类**：`time series, correlations`。这是单图的统计图形分析，不等同于02的完整信息图形成品类型。

## 1. 源码支持的字段配置
- **必需字段**：x（number/date）、y（number/date；可聚合，默认sum）。
- **可选字段**：lines（number/string/date）、color（number/string/date）、series（number/string/date）。
- 类型限定来自 [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/linechart/dimensions.js)，请区分必填、可选和多列映射；若聚合方式有选项，以代码和实际配置为准。

## A. 数据逻辑与统计任务（分析）
以可排序的连续/时间X值组织观测序列，分析Y随X变化；多线由lines字段标识。

## B. 数据重组与计算（源码及解释）
源码字段映射允许y聚合，是否求和必须根据重复X记录及数据口径判断。

## C. 视觉编码（点、线、面、位置、色彩等）
点的坐标位置决定数据值，线的方向与斜率说明变化，多颜色区分不同序列。

## D. 数据／信息架构
统一X范围→值及采样间隔→分组序列→轴范围→趋势注释和重要转折。

## E. 视觉叙事与观看路径
建立基期→演变→峰谷/转折→末期比较；可用多序列强调交叉与变化。

## 教学示例（分析人员构造，非原仓库原作）
年份×销售额、产品类别→各产品随时间变化。

## 误判与设计边界
连接线可能隐含区间连续；不规则采样点的间距需按实际时间处理；线条太多需筛选或小多图。

## 源码核对与可复现入口
[metadata.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/linechart/metadata.js) · [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/linechart/dimensions.js) · [mapping.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/linechart/mapping.js) · [render.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/linechart/render.js) · [visualOptions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/linechart/visualOptions.js)

[返回本组](README.md) · [返回总索引](../06-31图表检索总表.md)

> 证据分层：字段/原生分类/实际映射据源码；面向教学的适用问题、叙事和风险为研究归纳，尚未通过用户测试得出通用定律。
