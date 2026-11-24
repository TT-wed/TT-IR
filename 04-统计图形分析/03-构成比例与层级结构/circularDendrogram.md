# 环形树状图｜Circular dendrogram

> RAWGraphs Charts v1.1.0 已导出模块：`circularDendrogram`；**官方 metadata 类别**：`hierarchies, proportions`。信息图形设计判断与源码事实分别说明。

## 1. 源码数据映射
- 必需：hierarchy（多列number/date/string；multiple=true）。
- 可选：size（number，默认sum）、color（number/date/string）、label（多个number/date/string）。
- 这些槽位来自 [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/circularDendrogram/dimensions.js)，多层级路径并不等价于只提供一个父节点名称；参数的统计聚合应核对具体选项。

## A. 数据逻辑
把层级树的各分支向外环放射，适合较多叶节点的整体结构扫描。

## B. 统计/计算与布局
mapping.js与线性树状图一样读取hierarchy多列路径，render.js将树形节点转换为放射布局。

## C. 视觉编码
从圆心向外的节点半径层次表达深度，弧线与径向连线表达父子关系；大小、颜色可编码附加变量。

## D. 数据／信息架构
根→路径层级→叶节点→放射排序→径向标签和附加符号图例。

## E. 视觉叙事与阅读层级
从中心主题开始向周围探索各分支，观察类群占据的角区和分支数量。

## 教学构造示例（非RAWGraphs作者原作）
世界语言家族→语系→语支→语种结构。

## 设计风险与适用边界
角度位置主要由布局决定，不能据角距推断真实相似度；过多叶节点需要裁剪标签和交互。

## 源代码
[metadata.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/circularDendrogram/metadata.js) · [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/circularDendrogram/dimensions.js) · [mapping.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/circularDendrogram/mapping.js) · [render.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/circularDendrogram/render.js) · [visualOptions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/circularDendrogram/visualOptions.js)

[本组目录](README.md) · [31图总览](../06-31图表检索总表.md)

> 数据要求和明确的实现方式来自本次锁定源码，A–E中对传播效果的建议是研究归纳。
