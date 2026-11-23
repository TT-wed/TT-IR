# 地平线图｜Horizon graph

> 研究对象：RAWGraphs Charts v1.1.0，`src/horizongraph`；**源码原生分类**：`time series, correlations`。这是单图的统计图形分析，不等同于02的完整信息图形成品类型。

## 1. 源码支持的字段配置
- **必需字段**：x（number/date）。
- **可选字段**：y（number，默认聚合sum）、group（number/date/string）。
- 类型限定来自 [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/horizongraph/dimensions.js)，请区分必填、可选和多列映射；若聚合方式有选项，以代码和实际配置为准。

## A. 数据逻辑与统计任务（分析）
对同一连续区间内的数量曲线分组呈现，通过折叠色带压缩高度以容纳更多序列。

## B. 数据重组与计算（源码及解释）
mapping.js按group和x聚合Y值；render.js使用位置和颜色/层级显示数值区间。

## C. 视觉编码（点、线、面、位置、色彩等）
横轴仍表示连续位置，色带颜色/深度与偏离程度共同编码数值，减少垂直空间消耗。

## D. 数据／信息架构
时间/连续X→组别→数值范围和基准→色带层级→统一图例。

## E. 视觉叙事与观看路径
快速扫描多组峰谷及正负区间，发现同步波动和异常时间窗口。

## 教学示例（分析人员构造，非原仓库原作）
多个地区每月气温距平曲线→用相同色带基准做并列扫描。

## 误判与设计边界
缺少颜色标尺和基准解释难以直接读出绝对数值；不宜当作精确折线图替代。

## 源码核对与可复现入口
[metadata.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/horizongraph/metadata.js) · [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/horizongraph/dimensions.js) · [mapping.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/horizongraph/mapping.js) · [render.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/horizongraph/render.js) · [visualOptions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/horizongraph/visualOptions.js)

[返回本组](README.md) · [返回总索引](../06-31图表检索总表.md)

> 证据分层：字段/原生分类/实际映射据源码；面向教学的适用问题、叙事和风险为研究归纳，尚未通过用户测试得出通用定律。
