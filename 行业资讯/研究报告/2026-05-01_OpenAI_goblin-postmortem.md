# Where the Goblins Came From

**来源：** OpenAI Research Blog | **发布时间：** 2026-04-29
**链接：** https://openai.com/index/where-the-goblins-came-from
**分类：** 研究报告

---

## 核心内容

OpenAI 披露 GPT-5.1 起模型出现异常「goblin/gremlin」隐喻使用倾向的根因调查。问题根源为训练「Nerdy」人格定制功能时使用的高奖励信号无意间放大了生物词汇使用，导致强化学习反馈循环将行为泛化至所有输出。

发现时间线：
- GPT-5.1 发布后（11月）：用户反馈模型「过于熟悉」
- GPT-5.4：生物词汇引用大幅增加，启动深入调查
- GPT-5.5 Codex 测试：观察到对 goblin 隐喻的异常偏好

关键数据：
- 「goblin」提及量在 GPT-5.1 后增加 175%
- 「gremlin」增加 52%
- Nerdy 人格在所有 ChatGPT 响应中占 2.5%，却贡献了 66.7% 的「goblin」提及

根因：
- Nerdy 奖励信号对含 goblin/gremlin 等词汇的输出打分更高
- 76.2% 数据集显示生物词汇输出获得正提升
- 强化学习未将行为限制在 Nerdy 条件内，泛化至所有输出

修复措施：
- 停用 Nerdy 人格
- 移除 goblin 亲和奖励信号
- 过滤含生物词汇的训练数据
- Codex 中添加开发者提示指令

## 关键要点
- 训练奖励信号可导致意外的模型行为泛化，这是 RLHF 的重要教训
- OpenAI 开发了新工具用于审计模型行为并从根因修复问题
- Codex 用户可通过移除抑制指令重新启用 goblin 行为（极客模式）
- 其他生物词汇（Raccoons、Trolls、Ogres、Pigeons）也被识别为「tic words」
