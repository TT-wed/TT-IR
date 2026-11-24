# 气泡散点图｜Bubble chart

> RAWGraphs Charts `v1.1.0` 正式导出模块：`src/bubblechart`；**元数据原始分类**：`correlations, proportions`。

## 1. 数据字段（来自 dimensions.js）
- 必需：x（number/date）、y（number/date）。
- 可选：size（number）、color（number/date/string）、connectedBy（number/date）、label（多个number/date/string字段）、series（number/date/string）。
- 日期型、数值型和字符串型的界线按项目源码字段约束执行，不把分类值擅自当连续数量。

## A. 数据逻辑与分析问题
每个观测对象有两个定量坐标；可额外用气泡大小表示第三个数量变量，用颜色表示第四变量。

## B. 统计与源码实现
mapping.js为字段直接读取；render.js决定数值坐标、气泡面积/大小映射和避碰等布局选项，不能把视觉大小当精确值。

## C. 视觉编码
X/Y位置是主二维定量通道；大小表达第三值，颜色类别或数值；连接线须有明确的顺序含义。

## D. 数据／信息架构
对象ID→X、Y数值→size及color→坐标单位→气泡图例和标签管理。

## E. 视觉叙事架构
读者从关系/聚类入手，再聚焦体量异常的大气泡或特定颜色群。

## 教学构造示例（非官方样本）
国家的人均收入、预期寿命、人口→二维关系加气泡大小。

## 设计限制与替代判断
气泡面积与半径的区别必须说明；如果数据密集，改Hexbin/Contour看密度；关联不构成因果。

## 源码交叉验证
[metadata.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/bubblechart/metadata.js) · [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/bubblechart/dimensions.js) · [mapping.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/bubblechart/mapping.js) · [render.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/bubblechart/render.js) · [visualOptions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/bubblechart/visualOptions.js)。

[本组索引](README.md) · [31图总索引](../06-31图表检索总表.md)

> 字段/模块依据源码；A—E 的应用与误读警示为信息设计研究归纳，未经独立性能评测。
