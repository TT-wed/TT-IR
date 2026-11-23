# 排名变化图｜Bumpchart

> 研究对象：RAWGraphs Charts v1.1.0，`src/bumpchart`；**源码原生分类**：`time series, correlations, proportions`。这是单图的统计图形分析，不等同于02的完整信息图形成品类型。

## 1. 源码支持的字段配置
- **必需字段**：x（number/date）。
- **可选字段**：size（number，默认聚合sum）、rank（number，默认聚合sum）、streams（number/string/date）、series（number/string/date）。
- 类型限定来自 [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/bumpchart/dimensions.js)，请区分必填、可选和多列映射；若聚合方式有选项，以代码和实际配置为准。

## A. 数据逻辑与统计任务（分析）
追踪类别在连续时间/次序X上的排序变化；排名与绝对数量是不同变量。

## B. 数据重组与计算（源码及解释）
mapping.js按streams、series、x聚合size/rank；metadata写明默认依据流量size排序，也能映射rank字段。

## C. 视觉编码（点、线、面、位置、色彩等）
X为时间/连续阶段，纵向位置是名次，线段展现上升下降及互换。

## D. 数据／信息架构
比较对象→每期数值或排名→排序规则→各期名次→连线和关键节点标签。

## E. 视觉叙事与观看路径
强调谁超越谁、名次升降及交替，适合讨论竞争格局而非数值差。

## 教学示例（分析人员构造，非原仓库原作）
球队不同赛季排名→比较位置变化。

## 误判与设计边界
第一名和第二名可能数值差很小或很大；图形无法自行表达这种差值，要另附实际量表。

## 源码核对与可复现入口
[metadata.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/bumpchart/metadata.js) · [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/bumpchart/dimensions.js) · [mapping.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/bumpchart/mapping.js) · [render.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/bumpchart/render.js) · [visualOptions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/bumpchart/visualOptions.js)

[返回本组](README.md) · [返回总索引](../06-31图表检索总表.md)

> 证据分层：字段/原生分类/实际映射据源码；面向教学的适用问题、叙事和风险为研究归纳，尚未通过用户测试得出通用定律。
