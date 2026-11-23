# 圆形打包图｜Circle Packing

> RAWGraphs Charts v1.1.0 已导出模块：`circlepacking`；**官方 metadata 类别**：`hierarchies, proportions`。信息图形设计判断与源码事实分别说明。

## 1. 源码数据映射
- 必需：hierarchy（多列number/date/string；multiple=true）。
- 可选：size（number，默认sum）、color（number/date/string）、label（多个number/date/string）。
- 这些槽位来自 [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/circlepacking/dimensions.js)，多层级路径并不等价于只提供一个父节点名称；参数的统计聚合应核对具体选项。

## A. 数据逻辑
层级节点的子对象装入父对象圆形，面积呈现叶节点数量，并保留父子包含的树形语义。

## B. 统计/计算与布局
mapping.js逐级组织hierarchy路径、聚合size；render.js使用圆形打包算法确定各圆大小和位置。

## C. 视觉编码
圆面积表达数量、圆内包含关系表达层级、颜色辅助分组。

## D. 数据／信息架构
层级路径→数量权重→祖先节点聚合→嵌套圆→标签和图例。

## E. 视觉叙事与阅读层级
从最大父类进入细分结构，展示大类及其核心成员之间的视觉关系。

## 教学构造示例（非RAWGraphs作者原作）
商品主类→子类→单品销售件数。

## 设计风险与适用边界
圆之间留白并不对应“其他类别”或损失量；面积读数困难，不能把圆的半径误当比例本身。

## 源代码
[metadata.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/circlepacking/metadata.js) · [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/circlepacking/dimensions.js) · [mapping.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/circlepacking/mapping.js) · [render.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/circlepacking/render.js) · [visualOptions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/circlepacking/visualOptions.js)

[本组目录](README.md) · [31图总览](../06-31图表检索总表.md)

> 数据要求和明确的实现方式来自本次锁定源码，A–E中对传播效果的建议是研究归纳。
