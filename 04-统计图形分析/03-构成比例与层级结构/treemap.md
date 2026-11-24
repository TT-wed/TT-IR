# 矩形树图｜Treemap

> RAWGraphs Charts v1.1.0 已导出模块：`treemap`；**官方 metadata 类别**：`hierarchies, proportions`。信息图形设计判断与源码事实分别说明。

## 1. 源码数据映射
- 必需：hierarchy（多列number/date/string；multiple=true）。
- 可选：size（number，默认sum）、color（number/date/string）、label（多个number/date/string）。
- 这些槽位来自 [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/treemap/dimensions.js)，多层级路径并不等价于只提供一个父节点名称；参数的统计聚合应核对具体选项。

## A. 数据逻辑
每条记录具有若干级类别路径，按父子包含关系组织各级汇总；面积是可加数量的布局通道。

## B. 统计/计算与布局
mapping.js使用逐级聚合结构和数值聚合器，render.js创建分层数据并布局为嵌套矩形。

## C. 视觉编码
矩形的面积表示数量，包含关系映射为嵌套空间，颜色辅助区分分支或编码额外变量。

## D. 数据／信息架构
层级字段序列→叶节点数量→逐级汇总→矩形切分→标签、颜色与层级路径。

## E. 视觉叙事与阅读层级
先从总量看到主要分支占地，再在分支中寻找异常大/小叶节点，形成从整体到局部的探索。

## 教学构造示例（非RAWGraphs作者原作）
学院→专业→班级→人数，将各级学生人数分配到矩形面积。

## 设计风险与适用边界
小矩形可读性差；面积比较精度不如共基线条；必须排除双重汇总和无法相加的数据。

## 源代码
[metadata.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/treemap/metadata.js) · [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/treemap/dimensions.js) · [mapping.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/treemap/mapping.js) · [render.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/treemap/render.js) · [visualOptions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/treemap/visualOptions.js)

[本组目录](README.md) · [31图总览](../06-31图表检索总表.md)

> 数据要求和明确的实现方式来自本次锁定源码，A–E中对传播效果的建议是研究归纳。
