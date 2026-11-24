# 平行坐标图｜Parallel coordinates

> RAWGraphs Charts `v1.1.0` 正式导出模块：`src/parallelcoordinates`；**元数据原始分类**：`correlations, distributions`。

## 1. 数据字段（来自 dimensions.js）
- 必需：dimensions（多个number/date字段；multiple=true）。
- 可选：color（number/date/string）。
- 日期型、数值型和字符串型的界线按项目源码字段约束执行，不把分类值擅自当连续数量。

## A. 数据逻辑与分析问题
每一行观测跨越多个定量维度，每个维度单独形成一条平行标尺，记录连成折线。

## B. 统计与源码实现
mapping.js读取多个数值字段；render.js按各字段各自的数据域建立线性轴，配合透明度和颜色绘制多折线。

## C. 视觉编码
轴的位置是字段顺序、各轴上的点位是对应变量值，折线整体展示多维组合。

## D. 数据／信息架构
观测记录→数值字段清单→各字段域范围→平行轴序列→折线、色彩与异常识别。

## E. 视觉叙事架构
从一条变量轴筛选/观察高低值，再沿线条看多指标同升同降。

## 教学构造示例（非官方样本）
汽车的功率、油耗、质量、价格→多变量档位及关联。

## 设计限制与替代判断
各轴量纲、位置顺序及反向设置可显著改变视觉模式；大量记录会重叠。

## 源码交叉验证
[metadata.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/parallelcoordinates/metadata.js) · [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/parallelcoordinates/dimensions.js) · [mapping.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/parallelcoordinates/mapping.js) · [render.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/parallelcoordinates/render.js) · [visualOptions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/parallelcoordinates/visualOptions.js)。

[本组索引](README.md) · [31图总索引](../06-31图表检索总表.md)

> 字段/模块依据源码；A—E 的应用与误读警示为信息设计研究归纳，未经独立性能评测。
