# 斜率对比图｜Slope chart

> 研究对象：RAWGraphs Charts v1.1.0，`src/slopechart`；**源码原生分类**：`correlations`。这是单图的统计图形分析，不等同于02的完整信息图形成品类型。

## 1. 源码支持的字段配置
- **必需字段**：source（number/date）、target（number/date）。
- **可选字段**：name（number/date/string）、color（number/date/string）、series（number/string/date）。
- 类型限定来自 [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/slopechart/dimensions.js)，请区分必填、可选和多列映射；若聚合方式有选项，以代码和实际配置为准。

## A. 数据逻辑与统计任务（分析）
每对象只有两个可比较端点，斜率说明前后差异而非完整连续过程。

## B. 数据重组与计算（源码及解释）
mapping.js直接映射source、target、name、color、series，并未执行复杂聚合。

## C. 视觉编码（点、线、面、位置、色彩等）
两条平行数值位置轴的点通过线连接，线的上升/下降表示方向，线端点显示数值。

## D. 数据／信息架构
对象ID→起点值→终点值→差值方向→末端文字、颜色和共同尺度。

## E. 视觉叙事与观看路径
阅读从初始状态到末期状态的变化及反转，适用于前后比较。

## 教学示例（分析人员构造，非原仓库原作）
政策前后各地区某项指标→两端对照与上升下降。

## 误判与设计边界
仅两个时点不得推断中间过程的单调趋势；跨对象交叉太多时可改排序条形图。

## 源码核对与可复现入口
[metadata.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/slopechart/metadata.js) · [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/slopechart/dimensions.js) · [mapping.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/slopechart/mapping.js) · [render.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/slopechart/render.js) · [visualOptions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/slopechart/visualOptions.js)

[返回本组](README.md) · [返回总索引](../06-31图表检索总表.md)

> 证据分层：字段/原生分类/实际映射据源码；面向教学的适用问题、叙事和风险为研究归纳，尚未通过用户测试得出通用定律。
