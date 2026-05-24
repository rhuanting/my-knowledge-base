---
type: note
status: active
tags:
  - type/note
  - status/active
  - topic/work
---

# 好的 Skill 是给 Agent 的专业工作手册

## 核心观点

Skill 不是更长的 Prompt，也不是资料仓库，而是给 Agent 在某一类任务中使用的专业工作手册。

好的 Skill 应该让 Agent 更稳定地判断、行动和交付：知道什么时候使用这套能力，按什么流程做，遇到什么边界要停下来，以及哪些资源可以按需读取。

## Skill 适合沉淀什么

适合写进 Skill 的内容，是同类任务中会反复用到、且普通模型不一定天然知道的东西：

- 专业流程
- 判断标准
- 文件结构和命名规范
- 输出模板
- 常见失败模式
- 权限和安全边界
- 可复用脚本的使用方法
- 需要按需读取的参考资料入口

不适合写进 Skill 的内容：

- 空泛的性格要求
- Agent 本来就知道的通用常识
- 一次性任务背景
- 太长但不常用的资料
- 与技能目标无关的规则

判断标准：

```md
如果这条信息会在同类任务中反复帮助 Agent 做得更稳，就适合进入 Skill。
```

## description 是触发器

Skill 的 `description` 是最重要的部分，因为 Agent 是否会加载这个 Skill，主要取决于它。

差的写法：

```yaml
description: 用于知识库管理。
```

好的写法：

```yaml
description: Use when Codex needs to manage an Obsidian personal knowledge base, including capturing inbox notes, writing daily/weekly/monthly reviews, organizing tasks, extracting permanent notes, updating MOC map notes, and archiving completed or inactive content.
```

`description` 应该写清楚：

- 这个 Skill 解决什么任务
- 用户在什么场景下会触发它
- 它覆盖哪些具体操作
- 它适用于哪些文件、系统或领域

不要把“什么时候使用本 Skill”藏在正文里。正文只有在 Skill 已经触发之后才会被读取。

## SKILL.md 只放核心流程

`SKILL.md` 应该短而有力，重点写：

- 核心原则
- 标准工作流
- 必须遵守的边界
- 何时读取额外参考资料
- 何时调用脚本或使用资产
- 完成后的交付标准

复杂内容应该拆出去：

```text
my-skill/
├── SKILL.md
├── references/
│   ├── templates.md
│   └── classification-rules.md
├── scripts/
│   └── helper.py
└── assets/
    └── template.md
```

`references/` 放长规则、案例、API 文档、领域资料。  
`scripts/` 放稳定重复、容易出错、需要确定性的操作。  
`assets/` 放模板、图片、字体、示例文件、项目脚手架。

## 使用渐进披露

Skill 不应该让 Agent 每次都加载所有信息，而应该告诉它在什么情况下读取什么材料。

示例：

```md
If the task involves weekly review generation, read `references/weekly-review-template.md`.
If the task only creates a daily note, do not read additional references.
If the task requires bulk classification, read `references/classification-rules.md`.
```

这能减少上下文浪费，也能降低无关规则干扰判断的概率。

## 写流程，不写口号

差的写法：

```md
整理知识库时要认真、准确、符合规范。
```

好的写法：

```md
整理 Inbox 时：
1. 扫描 `00_Inbox` 中的文件。
2. 按任务、日记、项目、领域、永久笔记、资料、归档分类。
3. 不确定的内容保留在 `00_Inbox`，并说明原因。
4. 有长期价值的想法改写为 `05_Notes` 中的独立笔记。
5. 更新相关 `07_Maps`。
6. 最后汇总移动、创建、修改的文件。
```

Agent 不缺“要认真”的提醒，缺的是在具体场景下的可执行路径。

## 按风险设置自由度

Skill 要根据任务风险控制 Agent 的自由度。

高自由度适合：

- 写作
- 头脑风暴
- 观点整理
- 风格化表达

中自由度适合：

- 知识库整理
- 项目规划
- 资料归类
- 报告结构生成

低自由度适合：

- 文件格式转换
- API 调用
- 财务计算
- 批量修改
- 高风险权限操作

越容易造成不可逆后果，Skill 越应该给出明确步骤、脚本、检查点和用户确认规则。

## 明确停止和确认条件

好 Skill 不只告诉 Agent 做什么，也告诉它什么时候停下来。

应该明确：

- 删除文件前必须确认
- 覆盖已有内容前必须确认
- 大批量移动前必须确认
- 信息不足且会影响结果时必须提问
- 涉及隐私、安全、金钱、法律、医疗时提高确认门槛

示例：

```md
Before deleting, overwriting, or bulk-moving user files, ask for explicit confirmation and summarize the affected paths.
```

确认点不是降低效率，而是建立信任。

## 用少量高质量例子

Skill 中的例子应该覆盖典型任务和边界情况，而不是堆砌相似案例。

有效例子通常包括：

- 用户可能怎么说
- Agent 应该怎么判断
- 应该读取哪些资源
- 应该产出什么
- 什么情况下需要停下来问用户

3 到 5 个典型例子通常比 20 个相似例子更有用。

## Skill、Prompt、Tool 的边界

Skill、Prompt、Tool 不应互相替代。

| 内容 | 放哪里 |
|---|---|
| Agent 的身份、总体边界、默认工作方式 | Prompt |
| 某类任务的专业流程和判断标准 | Skill |
| 读写文件、搜索、调用 API、执行命令 | Tool |
| 大段参考资料、模板、规则表 | references / assets |
| 稳定重复的程序化操作 | scripts |

Prompt 负责调度和全局行为，Skill 负责专项方法，Tool 负责真实动作。

## 一个好 Skill 的检查清单

- `name` 简短、清晰、使用小写和连字符
- `description` 明确写出触发场景和具体任务
- `SKILL.md` 只保留核心流程，不堆资料
- 复杂资料拆到 `references/`
- 重复且易错的操作沉淀为 `scripts/`
- 模板和素材放进 `assets/`
- 写清楚何时读取额外资料
- 写清楚何时必须询问用户
- 用可执行步骤替代抽象口号
- 用少量典型例子覆盖关键场景
- 真实使用后持续补充失败模式和边界条件

## 最小模板

```md
---
name: skill-name
description: Use when Codex needs to ...
---

# Skill Name

## Core Rules

- ...

## Workflow

1. ...
2. ...
3. ...

## Stop And Ask

- ...

## References

- Read `references/x.md` when ...

## Completion

- Summarize what changed.
- List affected files.
- Mention unresolved questions or risks.
```

## 相关链接

- [[AI Agent 产品多出来的是智能边界与信任设计]]
- [[工作]]
