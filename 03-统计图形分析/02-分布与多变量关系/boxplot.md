# 箱线图｜Box plot

> RAWGraphs Charts `v1.1.0` 正式导出模块：`src/boxplot`；**元数据原始分类**：`distributions`。

## 1. 数据字段（来自 dimensions.js）
- 必需：value（number）。
- 可选：group（number/date/string）、color（number/string/date）。
- 日期型、数值型和字符串型的界线按项目源码字段约束执行，不把分类值擅自当连续数量。

## A. 数据逻辑与分析问题
对每组数值样本进行分位数概括，强调分散程度、中位数及离群点。

## B. 统计与源码实现
render.js排序后计算q1/q2/q3，IQR=q3−q1，须线用设置的iqrMultiplier裁到内部范围，单列超出部分作为离群点。

## C. 视觉编码
箱体上下边界是Q1/Q3，箱内线为中位数；须线与离群点表示扩展信息；组间对齐便于比较。

## D. 数据／信息架构
数值样本→可选分组→Q1、中位数、Q3、IQR→须线与离群值→坐标轴与组标签。

## E. 视觉叙事架构
先比中位数，再看波动、偏态和离群；用于讨论群组差异而不夸大个别点。

## 教学构造示例（非官方样本）
各地区城市人口样本→比较中位规模和分散程度。

## 设计限制与替代判断
源码metadata笼统写“五数概要”，但此实现须线通常不是实际最小/最大值；小样本量及分位算法需说明。

## 源码交叉验证
[metadata.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/boxplot/metadata.js) · [dimensions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/boxplot/dimensions.js) · [mapping.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/boxplot/mapping.js) · [render.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/boxplot/render.js) · [visualOptions.js](https://github.com/rawgraphs/rawgraphs-charts/blob/cade3b6e1b4d35d365440b1365d51b0dd48c9bce/src/boxplot/visualOptions.js)。

[本组索引](README.md) · [31图总索引](../06-31图表检索总表.md)

> 字段/模块依据源码；A—E 的应用与误读警示为信息设计研究归纳，未经独立性能评测。
