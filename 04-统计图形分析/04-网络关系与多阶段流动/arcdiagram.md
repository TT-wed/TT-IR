# 弧形网络图｜Arc Diagram

> RAWGraphs Charts v1.1.0 导出的 `src/arcdiagram`；metadata分类：`networks`。

## 1. 必须的数据结构与字段
- 必填字段：source（number/date/string）、target（number/date/string）。
- 可选字段：size（number，默认聚合sum）。
- 此组需要特别区分源目标**边表**与多个阶段分类**路径表**，二者不可直接互换。

## A. 基本数据逻辑
记录对象之间的边关系，以源节点和目标节点为关系两端；与时间序列或类别并列图不同，核心是连接而非差值。

## B. 统计/计算与实现
mapping.js对source/target连接按大小聚合；render.js将节点排成一条线，使用弧线绘制连接，源码引入louvain处理可选的社区排序。

## C. 视觉编码
水平节点位置表示排布顺序，弧线表示关系，线条跨度受节点次序影响；上/下方向可呈现关系方向。

## D. 数据／信息架构
节点字典→边表(source,target,size)→排序规则与节点位置→弧线、权重和图例。

## E. 视觉叙事
从主要节点观察连接密度与跨组关系，再关注孤立与枢纽节点。

## 可构造的教学案例
研究人员之间的论文引用边表→弧线显示跨群体联系。

## 易误判、数据伦理及替代图形
节点坐标和弧长不是地理距离；节点排序会强烈影响可读性，弧线交叉多时转为矩阵或其他网络图。

## 源码验证
[metadata.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/arcdiagram/metadata.js) · [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/arcdiagram/dimensions.js) · [mapping.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/arcdiagram/mapping.js) · [render.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/arcdiagram/render.js) · [visualOptions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/arcdiagram/visualOptions.js)

[本组索引](README.md) · [31图总表](../06-31图表检索总表.md)

> 源码中的具体字段和布局方法与本库提出的教学使用建议有明确区分。
