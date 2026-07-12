# agent-skills

这个仓库用于存放可复用的 AI agent skills。每个 skill 都是一个自包含目录，包含自己的 `SKILL.md`，用于说明触发条件、工作流程、行为边界和必要资源。

## Skills

| Skill | 简介 |
| --- | --- |
| [`guide-learning`](./skills/guide-learning/SKILL.md) | 引导学习地图、灵活路线、每日学习、资料筛选、苏格拉底提问、费曼验证和复习总结。 |
| [`guide-decisions`](./skills/guide-decisions/SKILL.md) | 澄清决策、识别约束与假设、比较方案取舍、给出建议并形成决策记录。 |

## guide-learning

`guide-learning` 是一个学习陪练 skill。它适合在用户想学习一门新技术或新概念时使用，让 AI 扮演学习陪练，而不是代劳者。

它的核心工作流是：

1. 先给学习地图，让用户决定学到哪一层。
2. 再根据用户基础和目标制定灵活学习路线，不默认写死每天做什么。
3. 每天围绕路线中的一步或几步独立推进学习。
4. 学习中筛选资料、讲概念，并适时用苏格拉底提问引导思考。
5. 结束前用费曼学习法检查用户是否真的理解。
6. 验证通过后输出一份复习用 Markdown 总结。

## guide-decisions

`guide-decisions` 是一个决策协作 skill。它适合在用户需要比较技术、产品、设计、规划或流程方案时使用，让 AI 主动整理信息、揭示取舍并给出建议，同时保留用户对价值取舍的最终拍板权。

它的核心工作流是：

1. 定义当前真正要作出的决定和范围。
2. 判断决定的影响、可逆性和紧迫程度。
3. 分开硬约束、成功标准、事实、假设和偏好。
4. 形成少量可行选项，并比较关键取舍。
5. 给出明确推荐、成立条件和可能的翻转点。
6. 设计验证动作，必要时输出 Markdown 决策记录。

## 使用方式

把需要使用的 skill 目录复制到你的 Codex skills 目录中，例如：

```text
~/.codex/skills/guide-learning/
```

复制后目录应包含：

```text
guide-learning/
  SKILL.md
  agents/
    openai.yaml

guide-decisions/
  SKILL.md
  agents/
    openai.yaml
```

然后在对话中自然提出学习或决策需求，或显式调用：

```text
Use $guide-learning to help me learn a new topic.
Use $guide-decisions to help me compare options and make a decision.
```

## 许可证

本仓库使用 MIT License。详见 [LICENSE](./LICENSE)。
