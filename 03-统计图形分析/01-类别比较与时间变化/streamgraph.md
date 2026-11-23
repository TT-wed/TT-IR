# 流图／流线面积图｜Streamgraph (area chart)

> 研究对象：RAWGraphs Charts v1.1.0，`src/streamgraph`；**源码原生分类**：`time series, correlations, proportions`。这是单图的统计图形分析，不等同于02的完整信息图形成品类型。

## 1. 源码支持的字段配置
- **必需字段**：x（number/date）。
- **可选字段**：size（number，默认聚合sum）、streams（number/string/date）、series（number/string/date）。
- 类型限定来自 [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/streamgraph/dimensions.js)，请区分必填、可选和多列映射；若聚合方式有选项，以代码和实际配置为准。

## A. 数据逻辑与统计任务（分析）
多个类别在同一连续区间上变化，通过堆叠带状面积观察构成和整体走势。

## B. 数据重组与计算（源码及解释）
mapping.js按series、streams、x聚合size；渲染将多条量序列组织为相邻面积带。

## C. 视觉编码（点、线、面、位置、色彩等）
横轴为X，彩色带的厚度表示系列大小；流图常使用非固定零基线减轻层叠视觉负担。

## D. 数据／信息架构
连续X→类别→各期数量→堆叠次序→总量/份额及图例。

## E. 视觉叙事与观看路径
展示不同类别的兴衰和比重演变，适合文化、媒体或消费结构变化。

## 教学示例（分析人员构造，非原仓库原作）
音乐形式各年营收→类别流量随年份变动。

## 误判与设计边界
带状颜色面积并不便于精确读出非最外侧系列；需要精确数值时辅以表格或堆叠柱。

## 源码核对与可复现入口
[metadata.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/streamgraph/metadata.js) · [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/streamgraph/dimensions.js) · [mapping.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/streamgraph/mapping.js) · [render.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/streamgraph/render.js) · [visualOptions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/streamgraph/visualOptions.js)

[返回本组](README.md) · [返回总索引](../06-31图表检索总表.md)

> 证据分层：字段/原生分类/实际映射据源码；面向教学的适用问题、叙事和风险为研究归纳，尚未通过用户测试得出通用定律。
