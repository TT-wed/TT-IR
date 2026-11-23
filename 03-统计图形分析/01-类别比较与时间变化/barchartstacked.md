# 堆叠柱状图｜Stacked bar chart

> 研究对象：RAWGraphs Charts v1.1.0，`src/barchartstacked`；**源码原生分类**：`correlations, proportions`。这是单图的统计图形分析，不等同于02的完整信息图形成品类型。

## 1. 源码支持的字段配置
- **必需字段**：stacks（number/string/date）、bars（多个number列；multiple=true）。
- **可选字段**：series（number/string/date）。
- 类型限定来自 [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/barchartstacked/dimensions.js)，请区分必填、可选和多列映射；若聚合方式有选项，以代码和实际配置为准。

## A. 数据逻辑与统计任务（分析）
同一类别由多项部分构成；各项相加形成总体（前提是单位及统计口径可加）。

## B. 数据重组与计算（源码及解释）
mapping.js对多个bars数值列聚合并供堆叠绘制；本模块要求多列数值输入。

## C. 视觉编码（点、线、面、位置、色彩等）
总柱高表示合计；各色段厚度编码构成量，底部段有共同基线、内部段则没有。

## D. 数据／信息架构
类别→各子项值→总量→堆叠顺序→图例和各部分数值说明。

## E. 视觉叙事与观看路径
从总体大小进入构成比较，适用于讨论“总量增长是由哪些部分驱动”。

## 教学示例（分析人员构造，非原仓库原作）
年度×支出构成（教育、医疗、交通等独立金额列）→构成和总额。

## 误判与设计边界
不同层的内部区段难精确比较；不要将不能相加的百分率或不同量纲硬堆叠。

## 源码核对与可复现入口
[metadata.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/barchartstacked/metadata.js) · [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/barchartstacked/dimensions.js) · [mapping.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/barchartstacked/mapping.js) · [render.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/barchartstacked/render.js) · [visualOptions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/barchartstacked/visualOptions.js)

[返回本组](README.md) · [返回总索引](../06-31图表检索总表.md)

> 证据分层：字段/原生分类/实际映射据源码；面向教学的适用问题、叙事和风险为研究归纳，尚未通过用户测试得出通用定律。
