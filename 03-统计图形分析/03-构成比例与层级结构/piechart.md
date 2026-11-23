# 饼图｜Pie chart

> RAWGraphs Charts v1.1.0 已导出模块：`piechart`；**官方 metadata 类别**：`proportions`。信息图形设计判断与源码事实分别说明。

## 1. 源码数据映射
- 必需：arcs（多个number数据列；multiple=true）。
- 可选：series（number/date/string）。
- 这些槽位来自 [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/piechart/dimensions.js)，多层级路径并不等价于只提供一个父节点名称；参数的统计聚合应核对具体选项。

## A. 数据逻辑
多个能相加的数值部分共同组成一个整体；该源码采用宽表多数值列映射，而非必然使用“类别/数值”两列长表。

## B. 统计/计算与布局
mapping.js通过getDimensionAggregator为每个arcs数值列取得聚合函数，按可选series汇总，组成扇区读数。

## C. 视觉编码
环绕圆周的各扇区角度/面积表达整体中的份额，各颜色标记子类别。

## D. 数据／信息架构
整体定义→数值列及其同口径性→求和和占比→扇区顺序→图例、标签与总量说明。

## E. 视觉叙事与阅读层级
先建立一个明确的100%整体，再引导读者识别主要构成与少数项。

## 教学构造示例（非RAWGraphs作者原作）
总预算的教育/交通/医疗/其他四个金额列→扇区构成。

## 设计风险与适用边界
组成值必须非负且可加；类别过多、占比相近时读数困难；需要精确比较应换排序条形图。

## 源代码
[metadata.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/piechart/metadata.js) · [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/piechart/dimensions.js) · [mapping.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/piechart/mapping.js) · [render.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/piechart/render.js) · [visualOptions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/piechart/visualOptions.js)

[本组目录](README.md) · [31图总览](../06-31图表检索总表.md)

> 数据要求和明确的实现方式来自本次锁定源码，A–E中对传播效果的建议是研究归纳。
