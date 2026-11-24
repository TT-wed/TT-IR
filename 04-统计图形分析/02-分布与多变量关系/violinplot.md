# 小提琴图｜Violin plot

> RAWGraphs Charts `v1.1.0` 正式导出模块：`src/violinplot`；**元数据原始分类**：`distributions`。

## 1. 数据字段（来自 dimensions.js）
- 必需：value（number）。
- 可选：group（number/date/string）、color（number/string/date）。
- 日期型、数值型和字符串型的界线按项目源码字段约束执行，不把分类值擅自当连续数量。

## A. 数据逻辑与分析问题
对连续数值在各区间的样本密度或频数分布绘制左右宽度，对比群组分布形态。

## B. 统计与源码实现
本版本render.js调用d3.bin().thresholds(binsNumber)分箱，并通过连接的分箱外形构建轮廓，不能默认写成KDE。

## C. 视觉编码
纵轴是值，形状的横向宽度是区间频数轮廓；可加原始点、颜色区分群组。

## D. 数据／信息架构
数值样本→分组→同一Y尺度→分箱数→两侧轮廓、点和标签。

## E. 视觉叙事架构
识别双峰、偏态、离散度及群组差异；与箱线图互补。

## 教学构造示例（非官方样本）
三所学校学生身高→比较峰值位置与分布范围。

## 设计限制与替代判断
bin数会改写轮廓光滑程度，少样本易产生假峰；不同组宜使用相同分箱尺度。

## 源码交叉验证
[metadata.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/violinplot/metadata.js) · [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/violinplot/dimensions.js) · [mapping.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/violinplot/mapping.js) · [render.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/violinplot/render.js) · [visualOptions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/violinplot/visualOptions.js)。

[本组索引](README.md) · [31图总索引](../06-31图表检索总表.md)

> 字段/模块依据源码；A—E 的应用与误读警示为信息设计研究归纳，未经独立性能评测。
