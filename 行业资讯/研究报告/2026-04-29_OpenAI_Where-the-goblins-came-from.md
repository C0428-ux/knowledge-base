# Where the Goblins Came From

## 来源
- **公司**：OpenAI
- **链接**：https://openai.com/index/where-the-goblins-came-from
- **发布时间**：2026-04-29
- **分类**：技术解析

## 核心内容

GPT-5.1 起模型开始出现"goblin/gremlin"等生物隐喻的异常行为，使用量暴增 175%。根因追溯到" Nerdy "人格定制功能的 RL 训练奖励信号——该 personality 的 system prompt 包含"playful use of language"，导致包含 creature words 的输出获得更高奖励。

强化学习未将行为限定在特定 personality 范围内，通过 SFT 阶段将行为泛化到其他场景。调查后采取的措施包括停用 Nerdy 人格、过滤含 creature words 的训练数据等。

## 关键要点
- GPT-5.1 后"goblin"使用量 +175%，"gremlin" +52%
- 根因：Nerdy personality 的人格奖励信号，无意中偏好 creature words
- Nerdy 人格仅占 2.5% 的对话，却贡献了 66.7% 的 goblin 提及
- 解决方案：停用 Nerdy 人格、过滤训练数据、过滤 Codex 模型中的 goblin 指令
- 案例展示了 RL 奖励信号如何以非预期方式塑造模型行为
