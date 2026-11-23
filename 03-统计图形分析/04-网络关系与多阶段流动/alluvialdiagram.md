# 冲积流图｜Alluvial Diagram

> RAWGraphs Charts v1.1.0 导出的 `src/alluvialdiagram`；metadata分类：`correlations, proportions`。

## 1. 必须的数据结构与字段
- 必填字段：steps（多个number/date/string字段；multiple=true）。
- 可选字段：size（number，默认sum；没有映射时按记录数统计）。
- 此组需要特别区分源目标**边表**与多个阶段分类**路径表**，二者不可直接互换。

## A. 基本数据逻辑
同一批对象沿多个分类维度的阶段路径变化：A类→B类→C类，不等于任意端点的自由网络边表。

## B. 统计/计算与实现
mapping.js对steps中的连续相邻列逐对d3.rollups，生成节点流；未映射size则按数量计，且过滤value<=0的边。

## C. 视觉编码
每阶段节点矩形的高度代表分类规模，跨阶段流带宽度代表共有对象的数量或权重。

## D. 数据／信息架构
每行对象→有序分类步骤→相邻步骤配对→计数/求和→逐列节点与相连流带。

## E. 视觉叙事
从起始类别追踪群体分化与合流，说明转移结构和变化去向。

## 可构造的教学案例
Titanic.tsv 的Class→Survival→Age group→Gender（项目自身sandbox配置）。

## 易误判、数据伦理及替代图形
步骤列是类别维度，不必然代表真实时间；若样本并非同一批对象则“流动”叙事可能误导；缺失值和过滤零值需说明。

## 源码验证
[metadata.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/alluvialdiagram/metadata.js) · [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/alluvialdiagram/dimensions.js) · [mapping.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/alluvialdiagram/mapping.js) · [render.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/alluvialdiagram/render.js) · [visualOptions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/alluvialdiagram/visualOptions.js)

[本组索引](README.md) · [31图总表](../06-31图表检索总表.md)

> 源码中的具体字段和布局方法与本库提出的教学使用建议有明确区分。
