# 甘特图｜Gantt chart

> 研究对象：RAWGraphs Charts v1.1.0，`src/ganttChart`；**源码原生分类**：`time series, correlations`。这是单图的统计图形分析，不等同于02的完整信息图形成品类型。

## 1. 源码支持的字段配置
- **必需字段**：startDate（number/date）、endDate（number/date）。
- **可选字段**：group（string）、color（string）。
- 类型限定来自 [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/ganttChart/dimensions.js)，请区分必填、可选和多列映射；若聚合方式有选项，以代码和实际配置为准。

## A. 数据逻辑与统计任务（分析）
各任务占据一个起止区间，重心是持续时间、重叠与先后，而非总量对比。

## B. 数据重组与计算（源码及解释）
mapping.js直接读取任务的开始和结束时间；CHANGLELOG v1.1.0增加X轴在顶部或底部的选项。

## C. 视觉编码（点、线、面、位置、色彩等）
区间条从开始到结束，条长对应持续跨度；垂直行位置编码任务分组。

## D. 数据／信息架构
任务→起始日期→结束日期→分组→任务顺序、时间刻度和项目里程碑注释。

## E. 视觉叙事与观看路径
说明计划安排、并行冲突和关键截止时间；既能教学也能作为工作排程。

## 教学示例（分析人员构造，非原仓库原作）
展览策划的选题、设计、印刷、布展各时间区间。

## 误判与设计边界
日期型必须确认时区和结束日期规则，任务依赖关系不应仅凭视觉相邻推断。

## 源码核对与可复现入口
[metadata.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/ganttChart/metadata.js) · [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/ganttChart/dimensions.js) · [mapping.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/ganttChart/mapping.js) · [render.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/ganttChart/render.js) · [visualOptions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/ganttChart/visualOptions.js)

[返回本组](README.md) · [返回总索引](../06-31图表检索总表.md)

> 证据分层：字段/原生分类/实际映射据源码；面向教学的适用问题、叙事和风险为研究归纳，尚未通过用户测试得出通用定律。
