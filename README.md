# agent-skills

这个仓库用于存放可复用的 AI agent skills。每个 skill 都是一个自包含目录，包含自己的 `SKILL.md`，用于说明触发条件、工作流程、行为边界和必要资源。

## Skills

| Skill | 简介 |
| --- | --- |
| [`guide-learning`](./skills/guide-learning/SKILL.md) | 引导学习地图、灵活路线、每日学习、资料筛选、苏格拉底提问、费曼验证和复习总结。 |
| [`guide-decisions`](./skills/guide-decisions/SKILL.md) | 澄清决策、识别约束与假设、比较方案取舍、给出建议并形成决策记录。 |
| [`guide-execution`](./skills/guide-execution/SKILL.md) | 引导用户逐步完成技术操作、判断反馈、处理异常并检查编码代理 Prompt。 |
| [`natural-reproduction-learning`](./skills/natural-reproduction-learning/SKILL.md) | 在真实技术任务中区分首次地图与自然复现模式，让 AI 补足具体缺口，同时保留用户的理解、判断和迁移能力。 |

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

## guide-execution

`guide-execution` 是一个执行陪练 skill。它适合在方向已经确定、用户希望亲自完成配置、部署、调试或排障时使用，让 AI 先说明阶段地图，再一次只给一个可验证步骤，并根据用户反馈继续。

它的核心工作流是：

1. 先说明当前目标、整体步骤和进入下一步的判断标准。
2. 每次只展开一个操作，解释目的、关键语法和预期输出。
3. 用户反馈前不继续；异常时先解释原因，再调整下一步。
4. 只索取必要的输出片段，让敏感信息尽量留在本地。
5. 用户亲自编写编码代理 Prompt 时，检查缺失、歧义、约束和验收。

## natural-reproduction-learning

`natural-reproduction-learning` 是一个面向真实技术工作的 AI 协作学习 skill。它适合用户希望借助 AI 高效完成任务，同时逐步建立对流程的理解、关键判断能力和可迁移的问题解决能力时使用。

它的核心工作流是：

1. 判断用户面对的是完全陌生的任务，还是已有经验可迁移的同类任务。
2. 首次接触时使用“首次地图模式”，由 AI 说明完整阶段、依赖关系、通用原理、具体细节和判断标准。
3. 再次处理同类任务时使用“自然复现模式”，由用户先回忆和推进，AI 只补当前缺口并简要提醒风险。
4. 当整体路线可能导致数据、安全、权限或结构性问题时，立即指出根本错误并回退到相应决策点。
5. 只在真实任务中观察用户能否恢复流程、迁移经验、定位卡点和针对性求助，不额外制造练习或要求背诵易变细节。

四个 skill 按主要结果和协作方式区分：想系统地**学会一个主题**时使用 `guide-learning`，需要**选方向**时使用 `guide-decisions`，方向已定并想在 AI 的逐步引导下**亲自做完**时使用 `guide-execution`；希望在 AI 深度参与真实工作的同时，通过后续同类任务**自然复现并内化经验**时使用 `natural-reproduction-learning`。请求同时包含明确学习意图和真实操作时，优先选择更符合用户期望的学习方式。

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

guide-execution/
  SKILL.md

natural-reproduction-learning/
  SKILL.md
```

然后在对话中自然提出学习、决策、执行或协作学习需求。

## 许可证

本仓库使用 MIT License。详见 [LICENSE](./LICENSE)。
