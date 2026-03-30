# guided-answering

[English](./README.en.md)

`guided-answering` 是一套用于提升回答质量的引导式回答规则。

它解决的不是“知识对不对”，而是“回答好不好用”这个问题。它主要针对这些常见情况：

- 简单问题被讲得过大、过空
- 模糊需求被直接当成明确需求开做
- 学习型问题一次塞太多内容
- 项目型问题一上来就铺很多方案，但用户不知道下一步该做什么

它的核心目标是：

- 先抓用户当前最想知道的核心
- 再判断该直接回答、逐步讲解，还是先收敛需求
- 只补当前必要的信息、约束、风险和前提

## 仓库结构

```text
guided-answering/
├─ SKILL.md
├─ SKILL.en.md
├─ README.md
├─ README.en.md
├─ .editorconfig
├─ .gitattributes
```

- `SKILL.md`：中文主版 skill
- `SKILL.en.md`：英文版 skill
- `README.md`：中文主版仓库说明
- `README.en.md`：英文版仓库说明

## 适合什么时候用

适合这些场景：

- 你想让模型先回答核心，不先铺一大段背景
- 你想让学习型问题按步骤推进，而不是一次讲完
- 你想让模糊需求先被收敛，再进入规划或实现
- 你想让模型在必要时补充约束，但不要把回答变成大课

## 它的工作方式

- 小问题：直接答
- 学习问题：一步一步讲
- 模糊需求：先压成最小可行版本
- 决策问题：给判断、边界和取舍

这不是单纯“少讲”，而是“先讲当前最有用的内容”。

## 常见工具用法

### Codex

把 `guided-answering` 目录复制到你的 Codex skills 目录下：

```text
$CODEX_HOME/skills/guided-answering
```

在 Windows 上，常见路径是：

```text
C:\Users\<your-user>\.codex\skills\guided-answering
```

调用方式：

```text
$guided-answering
```

### Claude Code / CC

如果你的环境支持本地 skill 或 slash command，可以把 `SKILL.md` 或 `SKILL.en.md` 作为规则来源接入。

如果没有原生 skill 机制，也可以直接把 `SKILL.md` 的内容放进：

- 项目级说明
- 会话级 system prompt
- 自定义行为 / 自定义指令

### Cursor

可以把这套规则放进：

- Project Rules
- 自定义系统提示词
- 团队共享提示模板

### 其他 AI 工具

只要工具支持以下任一能力，就可以使用这套规则：

- system prompt
- custom instructions
- reusable prompt template
- local skill / rule file

最简单的做法就是直接复用 `SKILL.md` 或 `SKILL.en.md`。

## License

仓库目前还没有附带许可证。
如果你准备公开发布，建议补一个 license，方便别人明确是否可以复用。
