# 弦图｜Chord Diagram

> RAWGraphs Charts v1.1.0 导出的 `src/chorddiagram`；metadata分类：`networks`。

## 1. 必须的数据结构与字段
- 必填字段：source（number/date/string）、target（number/date/string）。
- 可选字段：size（number，默认聚合sum）。
- 此组需要特别区分源目标**边表**与多个阶段分类**路径表**，二者不可直接互换。

## A. 基本数据逻辑
汇总网络节点之间的连接，强调各节点与其他节点的相对关联量；不是必然按时间组织。

## B. 统计/计算与实现
mapping.js以source和target构造加权连接；render.js使用d3的chord、arc、ribbon/ribbonArrow等几何表达。

## C. 视觉编码
圆周扇区表示节点及总关联规模；内部带宽表示连接量，颜色区分节点/来源。

## D. 数据／信息架构
边表→节点及方向口径→关联矩阵→圆周节点排序→连接带、图例与数字注释。

## E. 视觉叙事
让读者先看到重要节点，再发现节点对之间的强连接及交流结构。

## 可构造的教学案例
不同城市之间的迁移关系及人数流量→城市间联系强弱。

## 易误判、数据伦理及替代图形
圆周顺序决定连带交叉，连接过多易杂乱；方向/双向量不可凭视觉臆断，应明确流向和自环处理。

## 源码验证
[metadata.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/chorddiagram/metadata.js) · [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/chorddiagram/dimensions.js) · [mapping.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/chorddiagram/mapping.js) · [render.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/chorddiagram/render.js) · [visualOptions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/chorddiagram/visualOptions.js)

[本组索引](README.md) · [31图总表](../06-31图表检索总表.md)

> 源码中的具体字段和布局方法与本库提出的教学使用建议有明确区分。
