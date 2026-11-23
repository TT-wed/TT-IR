# 条形图／柱状图｜Bar chart

> 研究对象：RAWGraphs Charts v1.1.0，`src/barchart`；**源码原生分类**：`correlations`。这是单图的统计图形分析，不等同于02的完整信息图形成品类型。

## 1. 源码支持的字段配置
- **必需字段**：bars（number/string/date）。
- **可选字段**：size（number，默认聚合sum；未映射时按记录数计数）、color（number/string/date）、series（number/string/date）。
- 类型限定来自 [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/barchart/dimensions.js)，请区分必填、可选和多列映射；若聚合方式有选项，以代码和实际配置为准。

## A. 数据逻辑与统计任务（分析）
将记录按bars类别及可选series分组，每个组聚合一个数量；“长度/高度”是数量读数的主通道。

## B. 数据重组与计算（源码及解释）
mapping.js以d3.rollups按series、bars聚合；无size值时使用组内v.length计数。

## C. 视觉编码（点、线、面、位置、色彩等）
共基线上的水平条长或垂直柱高编码数量；位置区分类别，颜色可编码额外分组；可选择横纵方向与按数量/名称排序。

## D. 数据／信息架构
数据表→类别字典→分组和数量→排序→刻度、轴标签、图例和数据来源。

## E. 视觉叙事与观看路径
用排序体现极值、差异和排序；以“哪类最多、相差多少”发起读者任务。

## 教学示例（分析人员构造，非原仓库原作）
部门、员工数量→按部门显示员工人数；只有员工逐行表时可直接计数。

## 误判与设计边界
不把类别数字误读为连续数轴；注意零基线、单位和聚合口径。适合精确比较，信息不应靠插画代替柱长。

## 源码核对与可复现入口
[metadata.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/barchart/metadata.js) · [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/barchart/dimensions.js) · [mapping.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/barchart/mapping.js) · [render.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/barchart/render.js) · [visualOptions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/barchart/visualOptions.js)

[返回本组](README.md) · [返回总索引](../06-31图表检索总表.md)

> 证据分层：字段/原生分类/实际映射据源码；面向教学的适用问题、叙事和风险为研究归纳，尚未通过用户测试得出通用定律。
