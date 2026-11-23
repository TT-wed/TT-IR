# 六边形分箱图｜Hexagonal binning

> RAWGraphs Charts `v1.1.0` 正式导出模块：`src/hexagonalBinning`；**元数据原始分类**：`correlations, distributions`。

## 1. 数据字段（来自 dimensions.js）
- 必需：x（number/date）、y（number/date）。
- 可选：该模块dimensions.js仅列X、Y，六边格尺寸、颜色、计数标签在visualOptions.js内设置。。
- 日期型、数值型和字符串型的界线按项目源码字段约束执行，不把分类值擅自当连续数量。

## A. 数据逻辑与分析问题
先把二维空间均匀划成六边形格，再计算每格包含多少条数据，适用于大数据密度。

## B. 统计与源码实现
render.js依赖d3-hexbin，按六边网格的点计数生成格值；diameter控制箱格面积和分辨率。

## C. 视觉编码
位置显示二维数据平面，六边形颜色/大小表示局部计数密度。

## D. 数据／信息架构
原始点→X/Y尺度→六边网格→每格计数→数量色阶或大小图例。

## E. 视觉叙事架构
从整体密度分布寻找局部高峰和稀疏区，避免逐点阅读的负担。

## 教学构造示例（非官方样本）
城市居民两项连续测量10万记录→六边格热度展示。

## 设计限制与替代判断
bin大小、X/Y轴尺度和色彩域会显著影响结论；不同区域样本对比应统一参数。

## 源码交叉验证
[metadata.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/hexagonalBinning/metadata.js) · [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/hexagonalBinning/dimensions.js) · [mapping.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/hexagonalBinning/mapping.js) · [render.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/hexagonalBinning/render.js) · [visualOptions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/hexagonalBinning/visualOptions.js)。

[本组索引](README.md) · [31图总索引](../06-31图表检索总表.md)

> 字段/模块依据源码；A—E 的应用与误读警示为信息设计研究归纳，未经独立性能评测。
