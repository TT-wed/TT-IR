# Voronoi 邻域图｜Voronoi Diagram

> RAWGraphs Charts `v1.1.0` 正式导出模块：`src/voronoidiagram`；**元数据原始分类**：`Correlations`。

## 1. 数据字段（来自 dimensions.js）
- 必需：x（number/date）、y（number/date）。
- 可选：color（number/date/string）、label（多个number/date/string字段）。
- 日期型、数值型和字符串型的界线按项目源码字段约束执行，不把分类值擅自当连续数量。

## A. 数据逻辑与分析问题
以每个二维点为种子把平面划成“与该点距离最近”的邻域。

## B. 统计与源码实现
mapping.js直接映射位置字段，render.js按平面点位计算Voronoi胞元，属于几何邻域而非密度估计。

## C. 视觉编码
种子点的X/Y位置具有定量意义，胞元边界表达最近邻空间分割，色彩可附加类别。

## D. 数据／信息架构
二维样本坐标→Voronoi剖分→多边形胞元→种子点、标签、色彩图例。

## E. 视觉叙事架构
通过邻域大小和边界讨论点与点的空间竞争或稀疏度。

## 教学构造示例（非官方样本）
一组抽象平面样本点→比较最近邻影响范围。

## 设计限制与替代判断
胞元面积不是对象数量或权重；边界依赖研究区域截取，不应误称行政区或真实地图。

## 源码交叉验证
[metadata.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/voronoidiagram/metadata.js) · [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/voronoidiagram/dimensions.js) · [mapping.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/voronoidiagram/mapping.js) · [render.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/voronoidiagram/render.js) · [visualOptions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/voronoidiagram/visualOptions.js)。

[本组索引](README.md) · [31图总索引](../06-31图表检索总表.md)

> 字段/模块依据源码；A—E 的应用与误读警示为信息设计研究归纳，未经独立性能评测。
