# 桑基流向图｜Sankey Diagram

> RAWGraphs Charts v1.1.0 导出的 `src/sankeydiagram`；metadata分类：`networks`。

## 1. 必须的数据结构与字段
- 必填字段：source（number/date/string）、target（number/date/string）。
- 可选字段：size（number，默认sum）。
- 此组需要特别区分源目标**边表**与多个阶段分类**路径表**，二者不可直接互换。

## A. 基本数据逻辑
边表(source,target,value)表达节点间加权有向流，既能描述阶段过程也能描述一般网络流。

## B. 统计/计算与实现
mapping.js分组构造source/target/value；render.js调用d3-sankey-circular.sankeyCircular()，支持循环链接布局。

## C. 视觉编码
节点矩形的高度表示流量规模，连接带宽对应value，曲线及颜色说明流向或来源类别。

## D. 数据／信息架构
边表→节点去重→流量口径及方向→节点/边布局→流量图例、单位和异常支路说明。

## E. 视觉叙事
自主要来源追踪资金、能源或资源向后续节点的去向及回流。

## 可构造的教学案例
能源来源→处理→终端用途的分段流量；项目示例有sankey-loops.csv。

## 易误判、数据伦理及替代图形
要验证输入量、输出量、库存及损耗是否守恒；图宽不是长度/时长；循环连接不自动表示真实因果。

## 源码验证
[metadata.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/sankeydiagram/metadata.js) · [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/sankeydiagram/dimensions.js) · [mapping.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/sankeydiagram/mapping.js) · [render.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/sankeydiagram/render.js) · [visualOptions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/sankeydiagram/visualOptions.js)

[本组索引](README.md) · [31图总表](../06-31图表检索总表.md)

> 源码中的具体字段和布局方法与本库提出的教学使用建议有明确区分。
