# 雷达图｜Radar Chart

> RAWGraphs Charts `v1.1.0` 正式导出模块：`src/radarchart`；**元数据原始分类**：`correlations`。

## 1. 数据字段（来自 dimensions.js）
- 必需：axes（多个number字段；multiple=true）。
- 可选：color（number/string/date）、series（number/string/date）。
- 日期型、数值型和字符串型的界线按项目源码字段约束执行，不把分类值擅自当连续数量。

## A. 数据逻辑与分析问题
把多个数值指标以共同中心的辐射轴组织，可比较单个对象的多维轮廓。

## B. 统计与源码实现
mapping.js按series收集多列数值并聚合；metadata明确该实现各轴采用相同尺度。

## C. 视觉编码
各辐射轴上的离心距离编码指标值，连接形成多边形；颜色区分比较对象。

## D. 数据／信息架构
对象→若干具有可比较范围的指标→共用刻度→辐射轴顺序→面形与图例。

## E. 视觉叙事架构
观察轮廓强弱与指标短板；适合少数对象的小维数比较。

## 教学构造示例（非官方样本）
技能评价的五个同量表指标→观察优势和短板。

## 设计限制与替代判断
不同单位的原始值不可直接共享尺度，需先归一化并明确变换；轴顺序改变形状。

## 源码交叉验证
[metadata.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/radarchart/metadata.js) · [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/radarchart/dimensions.js) · [mapping.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/radarchart/mapping.js) · [render.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/radarchart/render.js) · [visualOptions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/radarchart/visualOptions.js)。

[本组索引](README.md) · [31图总索引](../06-31图表检索总表.md)

> 字段/模块依据源码；A—E 的应用与误读警示为信息设计研究归纳，未经独立性能评测。
