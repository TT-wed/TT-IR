# 03｜SGCS 中英文 JSON 配置规范

## 四种输出的唯一事实源
先完成一个**风格核心（Style Core）**，再通过主题自适应接口修改题材，最终将它编译成四类格式。不应分别独立撰写四套含不同风格细节的提示词，否则会发生“版本漂移”。

## 现有可复用文件
1. [English JSON canonical template](style-profile.template.en.json)：**机器端推荐作为唯一规范源**；全部13个系统完整列出，JSON语法有效。
2. [中文 JSON 模板](风格配置模板.zh.json)：语义相同、适合中文阅读与人工填写；字段键名为中文。
3. [JSON Schema](style-profile.schema.json)：适用于English版本的结构校验（2020-12），用于检查字段存在、类型等，不验证审美正确性。
4. [中英键名映射](字段中英对照.md)：用于数据同步和工作流实现。

## 填写规则
- `null` 表示尚未取得证据；`[]` 表示此阶段无列表条目；`{{THEME}}` 之类是**待替换的模板变量**，不是已提取结果。
- 只有确定参考来源和规则证据之后，才将 `status` 从 `unfilled` 改为 `draft`，经跨主题评估后才可称 `validated`。
- **Style Core十三项缺一不可**：不适用的字段明确记录“not_applicable”，不应填入拍脑袋的百分比。
- `subject_design` 记录**主体如何被画出来**的造型方法；`theme_adapter.current_subject` 记录**这次画的是什么**。两者必须分离。
- English JSON是基准，中文版是同步翻译。更改风格时先修正基准配置，再同步中文与其他输出；不可在不同版本里暗加额外风格要求。
- 参考图ID、规则置信度、模型版本及提示词变更需另行记录；JSON的结构正确不等于风格提取正确。

## 四种正式交付
参见 [04-提示词输出规范](../04-提示词输出规范/README.md)。中英JSON是配置形态，中文简易和自然语言是由同一配置编译生成的执行说明。

## 校验方式
Python可使用 `json.load` 检查模板语法；English模板可用支持JSON Schema Draft 2020-12的验证器检查 `style-profile.schema.json`。生成模型是否真正执行每条约束，必须通过[跨主题实验](../05-一致性校验/README.md)另行测试。
