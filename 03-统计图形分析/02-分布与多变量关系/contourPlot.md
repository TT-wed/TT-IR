# 二维等密度线图｜Contour plot

> RAWGraphs Charts `v1.1.0` 正式导出模块：`src/contourPlot`；**元数据原始分类**：`correlations, distributions`。

## 1. 数据字段（来自 dimensions.js）
- 必需：x（number/date）、y（number/date）。
- 可选：在本版本dimensions.js只定义X、Y两项；mapping.js出现weight读取配置，需注意接口与实现不完全一致。。
- 日期型、数值型和字符串型的界线按项目源码字段约束执行，不把分类值擅自当连续数量。

## A. 数据逻辑与分析问题
对二维点云估计密度，用一组相同密度等级的闭合线/区域代替大量重叠散点。

## B. 统计与源码实现
render.js依赖d3-contour构建等密度层，估计结果会受带宽、阈值和样本密度影响。

## C. 视觉编码
二维平面位置表示原始变量，等密度线/色阶表示点密度；线条本身不是时间轨迹。

## D. 数据／信息架构
二维数值点→密度估计网格→阈值层级→等值区域→色标与变量单位。

## E. 视觉叙事架构
帮助读者识别多峰/高密度中心，解释拥挤散点的主要分布。

## 教学构造示例（非官方样本）
两项考试成绩的10万条散点→看得分组合的集中区域。

## 设计限制与替代判断
平滑带宽越大，局部模式越可能被融合；密度差不等于组别区别；地图语义必须另有真实空间数据。

## 源码交叉验证
[metadata.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/contourPlot/metadata.js) · [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/contourPlot/dimensions.js) · [mapping.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/contourPlot/mapping.js) · [render.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/contourPlot/render.js) · [visualOptions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/contourPlot/visualOptions.js)。

[本组索引](README.md) · [31图总索引](../06-31图表检索总表.md)

> 字段/模块依据源码；A—E 的应用与误读警示为信息设计研究归纳，未经独立性能评测。
