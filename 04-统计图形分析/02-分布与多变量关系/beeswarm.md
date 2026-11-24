# 蜂群图｜Beeswarm plot

> RAWGraphs Charts `v1.1.0` 正式导出模块：`src/beeswarm`；**元数据原始分类**：`distributions, time series, proportions`。

## 1. 数据字段（来自 dimensions.js）
- 必需：xValue（number/date）。
- 可选：size（number/date）、color（number/string/date）、label（多个number/date/string字段）、series（number/string/date）。
- 日期型、数值型和字符串型的界线按项目源码字段约束执行，不把分类值擅自当连续数量。

## A. 数据逻辑与分析问题
保留每条记录的一个横轴值，并把同一区间的点错开避免重叠，直观呈现原始样本分布。

## B. 统计与源码实现
mapping.js直接保留每个观测点，并为没映射size的样本设默认尺寸；CHANGELOG v1.1.0加入只沿Y轴避碰移动点的选项。

## C. 视觉编码
X位置编码数值/日期；垂直位置主要负责防重叠，不应作为另一数量变量；圆面积和色彩可附加编码。

## D. 数据／信息架构
原始逐行观测→X数值→可选组别和尺寸→碰撞布局→轴、尺度和标签。

## E. 视觉叙事架构
让读者观察聚集区、稀疏区、离群点和不同群体的覆盖情况。

## 教学构造示例（非官方样本）
同学的阅读用时（每人一行）→用一组点显示个体分布。

## 设计限制与替代判断
Y位移通常只是排布，不是第二个变量；点数极多时仍遮挡；负值size可能触发警告。

## 源码交叉验证
[metadata.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/beeswarm/metadata.js) · [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/beeswarm/dimensions.js) · [mapping.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/beeswarm/mapping.js) · [render.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/beeswarm/render.js) · [visualOptions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/beeswarm/visualOptions.js)。

[本组索引](README.md) · [31图总索引](../06-31图表检索总表.md)

> 字段/模块依据源码；A—E 的应用与误读警示为信息设计研究归纳，未经独立性能评测。
