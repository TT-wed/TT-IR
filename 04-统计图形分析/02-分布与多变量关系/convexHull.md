# 凸包分组图｜Convex hull

> RAWGraphs Charts `v1.1.0` 正式导出模块：`src/convexHull`；**元数据原始分类**：`correlations, proportions`。

## 1. 数据字段（来自 dimensions.js）
- 必需：x（number/date）、y（number/date）。
- 可选：group（string）、label（多个number/date/string字段）。
- 日期型、数值型和字符串型的界线按项目源码字段约束执行，不把分类值擅自当连续数量。

## A. 数据逻辑与分析问题
用最小凸多边形包络一组二维点，强调分组范围与大致边界，而非精确概率密度。

## B. 统计与源码实现
mapping.js直接映射坐标/组名，render.js利用点位置计算凸包轮廓；极端点将决定边界。

## C. 视觉编码
二维位置编码数值，外包多边形区分组的空间包围范围；颜色辅助类别识别。

## D. 数据／信息架构
记录→二维坐标→group类别→分组点集→凸包边界和标注。

## E. 视觉叙事架构
比较群体的覆盖区域、重叠程度与离群边界，讨论区分度。

## 教学构造示例（非官方样本）
不同运动项目的身高与体重散点→比较群体范围重叠。

## 设计限制与替代判断
凸包仅表达外缘，不代表点密度、可信区间或聚类概率；对单个离群点敏感。

## 源码交叉验证
[metadata.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/convexHull/metadata.js) · [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/convexHull/dimensions.js) · [mapping.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/convexHull/mapping.js) · [render.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/convexHull/render.js) · [visualOptions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/convexHull/visualOptions.js)。

[本组索引](README.md) · [31图总索引](../06-31图表检索总表.md)

> 字段/模块依据源码；A—E 的应用与误读警示为信息设计研究归纳，未经独立性能评测。
