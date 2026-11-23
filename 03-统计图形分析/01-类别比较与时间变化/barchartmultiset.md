# 分组柱状图｜Multi-set bar chart

> 研究对象：RAWGraphs Charts v1.1.0，`src/barchartmultiset`；**源码原生分类**：`correlations, proportions`。这是单图的统计图形分析，不等同于02的完整信息图形成品类型。

## 1. 源码支持的字段配置
- **必需字段**：groups（number/string/date）、bars（多个number列；multiple=true）。
- **可选字段**：series（number/string/date）。
- 类型限定来自 [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/barchartmultiset/dimensions.js)，请区分必填、可选和多列映射；若聚合方式有选项，以代码和实际配置为准。

## A. 数据逻辑与统计任务（分析）
一个类别组内同时比较多个独立数值指标，是“组别×系列指标”的宽表结构。

## B. 数据重组与计算（源码及解释）
mapping.js为多列bars建立各自聚合器，并按groups及可选series组织记录。

## C. 视觉编码（点、线、面、位置、色彩等）
同组并列多根柱条，各指标使用相同数值尺度与分组标识；并列比堆叠更便于对照某一单项。

## D. 数据／信息架构
组别→指标列（多选）→组内并列柱→组间比较→颜色、单位、图例。

## E. 视觉叙事与观看路径
先观察单组内部差异，再横向比较不同组在相同指标上的变化。

## 教学示例（分析人员构造，非原仓库原作）
城市×各年度人均指标（各年度为独立数值列）→每城市一组并列柱。

## 误判与设计边界
指标必须量纲可比或明确多轴处理；类目或指标过多会密集。与堆叠柱不同，不主张整体加总。

## 源码核对与可复现入口
[metadata.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/barchartmultiset/metadata.js) · [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/barchartmultiset/dimensions.js) · [mapping.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/barchartmultiset/mapping.js) · [render.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/barchartmultiset/render.js) · [visualOptions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/barchartmultiset/visualOptions.js)

[返回本组](README.md) · [返回总索引](../06-31图表检索总表.md)

> 证据分层：字段/原生分类/实际映射据源码；面向教学的适用问题、叙事和风险为研究归纳，尚未通过用户测试得出通用定律。
