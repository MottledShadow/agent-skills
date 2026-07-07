# agent-skills

这个仓库用于存放可复用的 AI agent skills。每个 skill 都是一个自包含目录，包含自己的 `SKILL.md`，用于说明触发条件、工作流程、行为边界和必要资源。

## Skills

| Skill | 简介 |
| --- | --- |
| [`guide-learning`](./skills/guide-learning/SKILL.md) | 引导学习地图、灵活路线、每日学习、资料筛选、苏格拉底提问、费曼验证和复习总结。 |

## guide-learning

`guide-learning` 是一个学习陪练 skill。它适合在用户想学习一门新技术或新概念时使用，让 AI 扮演学习陪练，而不是代劳者。

它的核心工作流是：

1. 先给学习地图，让用户决定学到哪一层。
2. 再根据用户基础和目标制定灵活学习路线，不默认写死每天做什么。
3. 每天围绕路线中的一步或几步独立推进学习。
4. 学习中筛选资料、讲概念，并适时用苏格拉底提问引导思考。
5. 结束前用费曼学习法检查用户是否真的理解。
6. 验证通过后输出一份复习用 Markdown 总结。

## 使用方式

把需要使用的 skill 目录复制到你的 Codex skills 目录中，例如：

```text
~/.codex/skills/guide-learning/
```

复制后目录应包含：

```text
guide-learning/
  SKILL.md
```

然后在对话中自然提出学习需求，或显式调用：

```text
Use $guide-learning to help me learn a new topic.
```

## 许可证

本仓库使用 MIT License。详见 [LICENSE](./LICENSE)。
