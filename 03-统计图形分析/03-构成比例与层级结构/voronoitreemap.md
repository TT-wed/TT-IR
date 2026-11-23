# Voronoi 树图｜Treemap (Voronoi)

> RAWGraphs Charts v1.1.0 已导出模块：`voronoitreemap`；**官方 metadata 类别**：`hierarchies, proportions`。信息图形设计判断与源码事实分别说明。

## 1. 源码数据映射
- 必需：hierarchy（多列number/date/string；multiple=true）。
- 可选：size（number，默认sum）、color（number/date/string）、label（多个number/date/string）。
- 这些槽位来自 [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/voronoitreemap/dimensions.js)，多层级路径并不等价于只提供一个父节点名称；参数的统计聚合应核对具体选项。

## A. 数据逻辑
与矩形树图使用相同的层级路径与数值分配，但采用不规则Voronoi胞元承载叶节点比例。

## B. 统计/计算与布局
render.js使用d3-voronoi-treemap进行迭代布局；metadata明确提醒胞元面积可能不完全准确对应映射值。

## C. 视觉编码
不规则多边形的相对面积表达权重、空间包围表达父子层级，颜色提供分支类别。

## D. 数据／信息架构
层级与叶节点值→聚合→Voronoi迭代切割→子胞元、图例与分支标注。

## E. 视觉叙事与阅读层级
突出分支整体的视觉有机形态与部分构成，适合探索式或展示型叙事。

## 教学构造示例（非RAWGraphs作者原作）
生态类群→物种→观察数量的不规则地图式构成展示（非真实地图坐标）。

## 设计风险与适用边界
面积拟合误差是原作者确认的实现限制；不能用它要求读者精确反推百分比，应给出数字标签。

## 源代码
[metadata.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/voronoitreemap/metadata.js) · [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/voronoitreemap/dimensions.js) · [mapping.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/voronoitreemap/mapping.js) · [render.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/voronoitreemap/render.js) · [visualOptions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/voronoitreemap/visualOptions.js)

[本组目录](README.md) · [31图总览](../06-31图表检索总表.md)

> 数据要求和明确的实现方式来自本次锁定源码，A–E中对传播效果的建议是研究归纳。
