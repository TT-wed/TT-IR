# 线性树状图｜Linear dendrogram

> RAWGraphs Charts v1.1.0 已导出模块：`dendrogram`；**官方 metadata 类别**：`hierarchies, proportions`。信息图形设计判断与源码事实分别说明。

## 1. 源码数据映射
- 必需：hierarchy（多列number/date/string；multiple=true）。
- 可选：size（number，默认sum）、color（number/date/string）、label（多个number/date/string）。
- 这些槽位来自 [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/dendrogram/dimensions.js)，多层级路径并不等价于只提供一个父节点名称；参数的统计聚合应核对具体选项。

## A. 数据逻辑
以根→分支→叶节点的路径为核心，首要信息是父子关系而非严格数量大小。

## B. 统计/计算与布局
mapping.js按多层级数据构造节点结构，render.js用树形布局排布并绘制节点与父子连线。

## C. 视觉编码
连线表达父子关系，横向层级位置表达深度，节点大小/色彩可附加编码数量与类别。

## D. 数据／信息架构
叶节点属性→层级ID/父子路径→分支树→节点标签及根节点说明。

## E. 视觉叙事与阅读层级
从根节点逐步追踪分类系谱和组织结构，强调路径、从属和分叉。

## 教学构造示例（非RAWGraphs作者原作）
艺术流派的上级分类与细分门类谱系。

## 设计风险与适用边界
一棵展示树不自动证明进化时间或因果；枝条长度往往由布局设定，不一定代表差异或距离。

## 源代码
[metadata.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/dendrogram/metadata.js) · [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/dendrogram/dimensions.js) · [mapping.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/dendrogram/mapping.js) · [render.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/dendrogram/render.js) · [visualOptions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/dendrogram/visualOptions.js)

[本组目录](README.md) · [31图总览](../06-31图表检索总表.md)

> 数据要求和明确的实现方式来自本次锁定源码，A–E中对传播效果的建议是研究归纳。
