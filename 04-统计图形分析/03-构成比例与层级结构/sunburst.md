# 旭日图｜Sunburst diagram

> RAWGraphs Charts v1.1.0 已导出模块：`sunburst`；**官方 metadata 类别**：`hierarchies, proportions`。信息图形设计判断与源码事实分别说明。

## 1. 源码数据映射
- 必需：hierarchy（多列number/date/string；multiple=true）。
- 可选：size（number，默认sum）、color（number/date/string）、label（多个number/date/string）。
- 这些槽位来自 [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/sunburst/dimensions.js)，多层级路径并不等价于只提供一个父节点名称；参数的统计聚合应核对具体选项。

## A. 数据逻辑
用多层同心圆将根节点逐层分解，角度分配反映分支数值占比，径向层表示层级深度。

## B. 统计/计算与布局
render.js构建d3.hierarchy后使用d3.partition，节点角度范围承载数值汇总。

## C. 视觉编码
扇区角度/弧长编码数量分配，径向层数表达层级深度，色彩表达分支身份。

## D. 数据／信息架构
根目录→多列层级路径→叶节点数值→父节点汇总→圆环区段及标签。

## E. 视觉叙事与阅读层级
从圆心到外圈依次展开主题层次，兼顾总体构成与深度展开。

## 教学构造示例（非RAWGraphs作者原作）
组织→部门→岗位→人数的分层比例。

## 设计风险与适用边界
内圈和外圈面积不应混淆；扇区角度小、层级深时标注和精确比较受限。

## 源代码
[metadata.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/sunburst/metadata.js) · [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/sunburst/dimensions.js) · [mapping.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/sunburst/mapping.js) · [render.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/sunburst/render.js) · [visualOptions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/sunburst/visualOptions.js)

[本组目录](README.md) · [31图总览](../06-31图表检索总表.md)

> 数据要求和明确的实现方式来自本次锁定源码，A–E中对传播效果的建议是研究归纳。
