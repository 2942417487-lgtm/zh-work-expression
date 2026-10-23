# 中文工作表达 · zh-work-expression

基于 ASD-STE100（简化技术英语）核心原则，为中文语境和桌面端 Codex／ChatGPT Work 设计的非官方表达约束适配版。

让工作回复清楚、具体、有判断，并把工程上的严谨落实到验收条件、验证结果和下一步行动。

## 它会做什么

- **先回答问题。** 给出结论与必要依据，按内容选择段落、步骤或表格。
- **保留原意。** 保留事实、数字、条件、例外、否定和不确定性。
- **作出选择。** 比较方案时，结合目标和约束给出首选及关键取舍。
- **直接表达。** 用实际情况和成立条件说明问题，减少句尾例行追加的防御性限制语。
- **让验证有用。** 说明关键检查的对象与结果，发现验收缺口后继续处理已授权工作。

适合分析建议、进展汇报、交付说明、工作文档，以及文本改写与表达审查。创作和个人消息沿用用户指定的文风。

## 安装到 Codex

1. 在仓库页面选择 **Code → Download ZIP**，解压后将文件夹改名为 `zh-work-expression`。确认该目录内直接包含 SKILL.md，再将完整文件夹放入 Codex 的用户 skill 目录。
2. 新建聊天，在 skill 选择器中找到“中文工作表达”，或输入 `$zh-work-expression` 显式调用。
3. 如果选择器尚未出现该 skill，重启应用后再检查。

当前官方文档列出的用户目录是 `~/.agents/skills`。Windows 可在文件资源管理器中输入 `%USERPROFILE%\.agents\skills`；macOS／Linux 使用 `~/.agents/skills`。也可以放入项目的 `.agents/skills` 目录，供该项目使用。[官方安装与加载说明](https://learn.chatgpt.com/docs/build-skills)

最终目录结构：

```text
skills/
└── zh-work-expression/
    ├── SKILL.md
    ├── README.md
    ├── agents/
    │   └── openai.yaml
    └── references/
        └── examples.md
```

使用本地目录安装时，先解压 ZIP，再放入完整文件夹。

## 设置为长期默认规则

安装后，可把下面代码块中的正文追加到全局 `~/.codex/AGENTS.md`。保留原有内容，粘贴时省去外层三反引号。Windows 对应 `%USERPROFILE%\.codex\AGENTS.md`；设置了 `CODEX_HOME` 时使用该目录中的 AGENTS.md。

```markdown
## 中文工作表达

中文工作沟通默认应用已安装的“中文工作表达”（zh-work-expression）skill。首次撰写相关回复或文档前读取完整规则，上下文中缺失时重新加载。

先给答案，保留原意，比较方案给出有依据的首选；用实际证据描述完成状态，把验收缺口落实为行动。限制信息仅在影响选择、执行或验收时说明一次。项目执行有歧义先澄清，日常对话在回答完整处结束。

加载遇到问题时，说明具体原因，并按上面的核心规则工作。
```

全局 AGENTS.md 为后续 Codex 任务提供默认指令；项目 AGENTS.md 在对应项目范围内应用。修改后新建聊天核验读取。[官方 AGENTS.md 说明](https://learn.chatgpt.com/docs/agent-configuration/agents-md)

## 在 ChatGPT Work 中使用

1. 将完整的 `zh-work-expression` 文件夹打包为 ZIP，包内保留一个同名顶层文件夹。
2. 在提供 Skills 上传入口的 Work 环境中上传，完成界面的安装或启用步骤。
3. 在聊天中选择“中文工作表达”。ChatGPT 的 skill 选择入口支持 `@` 提及，具体入口以当前界面为准。

长期使用时，可将上面的规则正文加入目标端提供的自定义指令或项目指令入口，并在该环境中安装此 skill。各端首次启用时分别核验。[官方 skill 使用方式](https://learn.chatgpt.com/docs/build-skills)

## 使用示例

```text
请使用“中文工作表达”分析这三个方案，并根据我的约束给出首选。
```

```text
按“中文工作表达”改写下面的交付说明，保留事实、条件和不确定性。
```

```text
只审查这段回复：指出套话、冗余限制语，以及缺少验证依据的结论。
```

例如，浏览器兼容性验收进行到一半时：

> Chrome 导入通过。接下来在 Safari 上传同一文件，检查导入和打开结果。

这句话同时给出了检查结果、进度和下一步。

## 怎样确认已经加载

在新聊天中要求读取此 skill，报告其来源及“判断与澄清”部分的两条规则，然后回答：

> A 上手最快但无法本地部署，B 可以本地部署且维护量适中，C 可以本地部署但需要专人运维。我要求本地部署且没有专职运维，选哪个？

查看实际读取文件或调用 skill 的记录。本例应首选 B，并说明部署要求与维护人手这两个依据。

## 文件说明

| 文件 | 用途 |
|---|---|
| `SKILL.md` | 核心约束与工作方式 |
| `agents/openai.yaml` | 界面名称与自动匹配设置 |
| `references/examples.md` | 20 个按需查阅的适用案例 |
| `README.md` | 面向使用者的安装和使用说明 |

安装时保留完整文件夹。核心规则通过 SKILL.md 加载，案例按需读取，README 供使用者查阅。

## 来源与适配

本项目借鉴 ASD-STE100 的术语一致、动作明确和减少歧义等原则，并结合中文表达习惯重新设计。中文规则保留自然省略、必要程度与不确定性，按任务选择表达结构。

参考项目：

- [danyuchn/asd-ste100-skill](https://github.com/danyuchn/asd-ste100-skill)：消除歧义与改写保真。
- [woosal1337/blog 的 asd-ste100](https://github.com/woosal1337/blog/tree/main/videos/ep01-the-cure-for-ai-slop/asd-ste100)：回复结构与工作表达。
- [ASD-STE100 官方网站](https://www.asd-ste100.org/)：简化技术英语标准来源。

当前版本：1.1.0。
