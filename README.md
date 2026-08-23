# Evidence-led Writing｜证据主导写作

一个用于起草、审查和改写专业文本的 Agent Skill。它会隔离已经否决或与正文无关的讨论分支，围绕证据能够支持的核心主张组织内容，删除无必要的反驳和自我削弱表达，同时保留真正影响准确性、风险和决策的边界。

## 解决什么问题

- 最终正文仍在回答讨论中已经放弃的问题；
- 为了显得严谨，反复解释“本文不是什么、没有做什么”；
- 把必要的范围限定、风险或反例误删成“防御性写作”；
- 润色过程中无证据地提高确定性、因果性或适用范围；
- 把提议、报告、观察、结果和因果判断混成同一种证据。

## 安装

```bash
npx skills add baiyu-game/evidence-led-writing@evidence-led-writing
```

也可以把仓库复制到 Agent 使用的 Skills 目录。Codex 的个人 Skill 通常位于 `~/.codex/skills/evidence-led-writing/`。

## 使用

```text
$evidence-led-writing 检查这份方案里的防御性写作，先列问题，不要直接改写。
```

```text
$evidence-led-writing 把这份报告改成可直接提交的版本，保留会影响决策的风险和适用范围。
```

```text
$evidence-led-writing 讨论中已经否决了方案 B。整理最终稿时不要让这个废弃分支以反驳或免责声明的形式进入正文。
```

## 核心护栏

- 证据决定主张上限，不用更强语气冒充更强证据；
- 模式命中只是审查线索，不能靠禁词表机械删除；
- 必要边界避免无功能重复，但必须放在真正约束主张的位置；
- 材料不足时缩小表述或标记 `QUERY`，不编造事实与机制；
- 改写后检查主张强度、证据状态、风险边界和废弃分支是否发生漂移。

## 仓库结构

```text
.
├── SKILL.md
├── agents/
│   └── openai.yaml
├── evals/
│   └── cases.md
└── LICENSE
```

行为测试关注语义不变量，而不是要求模型输出固定措辞，见 [`evals/cases.md`](evals/cases.md)。

## License

MIT
