# 矩阵图｜Matrix Plot

> RAWGraphs Charts `v1.1.0` 正式导出模块：`src/matrixplot`；**元数据原始分类**：`correlations, time series, proportions`。

## 1. 数据字段（来自 dimensions.js）
- 必需：x（number/date/string）、y（number/date/string）。
- 可选：size（number，默认聚合sum）、color（number/date/string）、label（多个number/date/string字段）。
- 日期型、数值型和字符串型的界线按项目源码字段约束执行，不把分类值擅自当连续数量。

## A. 数据逻辑与分析问题
把两个分类/离散维度分别作为行列交叉索引，并对格子的数量或数值进行聚合。

## B. 统计与源码实现
mapping.js按x、y组合汇总大小和色彩，并可汇集多个标签；若没有size字段，需要核对默认计数。

## C. 视觉编码
横纵轴是类别位置；方形/圆形标记的尺寸或颜色表示交叉单元的数值。

## D. 数据／信息架构
行类目→列类目→交叉值矩阵→排序与缺失格→图例及整体模式。

## E. 视觉叙事架构
揭示哪些类别组合更频繁或强度更高；可从整体热点深入具体单元。

## 教学构造示例（非官方样本）
部门×问题类型的投诉数→识别集中出现的类别交叉。

## 设计限制与替代判断
显示为空的格子可能是零值或缺失值，不可混淆；数值维度映射到大小时精度不如位置。

## 源码交叉验证
[metadata.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/matrixplot/metadata.js) · [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/matrixplot/dimensions.js) · [mapping.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/matrixplot/mapping.js) · [render.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/matrixplot/render.js) · [visualOptions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/matrixplot/visualOptions.js)。

[本组索引](README.md) · [31图总索引](../06-31图表检索总表.md)

> 字段/模块依据源码；A—E 的应用与误读警示为信息设计研究归纳，未经独立性能评测。
