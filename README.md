# agent-skills

这个仓库用于存放可复用的 AI agent skills。每个 skill 都是一个自包含目录，包含自己的 `SKILL.md`，用于说明触发条件、工作流程、行为边界和必要资源。

## Skills

| Skill | 简介 |
| --- | --- |
| [`guide-learning`](./skills/guide-learning/SKILL.md) | 面向概念体系、原理和通用技能，引导学习地图、练习、苏格拉底提问、费曼验证和复习总结。 |
| [`guide-decisions`](./skills/guide-decisions/SKILL.md) | 澄清决策、识别约束与假设、比较方案取舍、给出建议并形成决策记录。 |
| [`guide-practical-learning`](./skills/guide-practical-learning/SKILL.md) | 在真实技术任务中按经验切换首次地图、引导执行和自然复现，通过反馈闭环逐渐把推进权还给用户。 |

## guide-learning

`guide-learning` 是一个知识建构型学习陪练 skill。它适合用户系统学习数学、理论知识、概念体系或课程式通用技能时使用，让 AI 扮演学习陪练，而不是代劳者。

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

## guide-practical-learning

`guide-practical-learning` 是一个真实任务型学习 skill。它适合用户亲自完成配置、部署、调试、排障、迁移或维护，并希望逐渐掌握通用流程和关键判断时使用。

它的核心工作流是：

1. 根据用户经验在首次地图、引导执行和自然复现之间切换。
2. 首次接触时说明阶段、依赖、风险、通用结构和环境特有细节。
3. 引导执行时一次推进一个可验证操作单元，根据真实反馈调整下一步。
4. 已有经验时由用户先恢复路线，AI 只补当前缺口并逐渐退场。
5. 高风险或根本路线错误时停止推进，保全状态并回退到相应决策点。
6. 完成阶段时总结已确认状态、形成的关键判断和剩余风险，不自动扩展任务。

三个 skill 按任务性质区分：想系统地**理解和掌握概念体系**时使用 `guide-learning`，需要在多个可行方向中**作出选择**时使用 `guide-decisions`，希望在真实环境中**亲自做成并逐渐学会推进**时使用 `guide-practical-learning`。后者再根据用户经验选择首次地图、引导执行或自然复现模式。

## 使用方式

把需要使用的 skill 目录复制到你的 Codex skills 目录中，例如：

```text
~/.codex/skills/guide-learning/
```

复制后目录应包含：

```text
guide-learning/
  SKILL.md

guide-decisions/
  SKILL.md

guide-practical-learning/
  SKILL.md
```

然后在对话中自然提出知识学习、决策或真实任务学习需求。

## 许可证

本仓库使用 MIT License。详见 [LICENSE](./LICENSE)。
