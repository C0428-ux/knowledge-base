# OpenAI GPT-5.5 发布内容

**来源：** OpenAI 官方发布页面  
**发布日期：** 2026年4月23日  
**原文链接：**  
- https://openai.com/index/introducing-gpt-5-5/
- https://openai.com/index/gpt-5-5-system-card/

---

## 一、产品概述

GPT-5.5 是 OpenAI 发布的"最智能、最具直觉性的模型"，专为实际计算机工作设计。

### 核心提升

- **更快速理解用户意图** — 所需 token 更少
- **更强的自主智能体能力** — 可规划、使用工具、检查工作、处理模糊性
- **保持 GPT-5.4 延迟水平** — 智能度大幅提升但延迟不变
- **Codex 任务 token 效率显著提升**

### 核心优势领域

智能体编码、计算机使用、知识工作、早期科学研究

---

## 二、模型版本

| 版本 | 描述 | 可用性 |
|------|------|--------|
| **GPT-5.5** | 标准通用模型 | Plus, Pro, Business, Enterprise |
| **GPT-5.5 Pro** | 高精度版本，适用于高要求任务 | Pro, Business, Enterprise |
| **GPT-5.5 Thinking** | 更快速响应，答案更智能简洁 | Plus, Pro, Business, Enterprise |

---

## 三、性能基准测试

### 3.1 编码基准

| 评测 | GPT-5.5 | GPT-5.4 | GPT-5.5 Pro | Claude Opus 4.7 | Gemini 3.1 Pro |
|------|---------|---------|-------------|----------------|----------------|
| Terminal-Bench 2.0 | **82.7%** | 75.1% | — | 69.4% | 68.5% |
| SWE-Bench Pro | **58.6%** | 57.7% | — | 64.3% | 54.2% |
| Expert-SWE (内部) | **73.1%** | 68.5% | — | — | — |

### 3.2 专业/知识工作

| 评测 | GPT-5.5 | GPT-5.4 | Claude Opus 4.7 | Gemini 3.1 Pro |
|------|---------|---------|-----------------|----------------|
| GDPval (胜率/平局) | **84.9%** | 83.0% | 80.3% | 67.3% |
| OSWorld-Verified | **78.7%** | 75.0% | 78.0% | — |
| Tau2-bench Telecom | **98.0%** | 92.8% | — | — |

### 3.3 学术/科学

| 评测 | GPT-5.5 | GPT-5.4 | GPT-5.5 Pro |
|------|---------|---------|-------------|
| GeneBench | **25.0%** | 19.0% | 33.2% |
| FrontierMath Tier 1-3 | **51.7%** | 47.6% | 52.4% |
| FrontierMath Tier 4 | **35.4%** | 27.1% | 39.6% |
| GPQA Diamond | **93.6%** | 92.8% | 94.4% |

### 3.4 长上下文 (256K-1M)

| 评测 | GPT-5.5 | GPT-5.4 |
|------|---------|---------|
| MRCR v2 256K-512K | **81.5%** | 57.5% |
| MRCR v2 512K-1M | **74.0%** | 36.6% |
| Graphwalks BFS 1M f1 | **45.4%** | 9.4% |

### 3.5 网络安全

| 评测 | GPT-5.5 | GPT-5.4 |
|------|---------|---------|
| CyberGym | **81.8%** | 79.0% |
| CTF Challenge Tasks | **88.1%** | 83.7% |

---

## 四、核心能力详解

### 4.1 智能体编码 (Agentic Coding)

- **Terminal-Bench 2.0：** 82.7% 准确率 (SOTA)
- **SWE-Bench Pro：** 58.6% 端到端任务完成率
- **Expert-SWE：** 73.1% (中位任务时长20小时)
- 跨大型代码库的上下文保留能力提升
- 调试、重构、测试、验证能力增强

**早期测试者评价：**

> "这是我用过的第一个具有真正概念清晰度的编码模型。"
> — Dan Shipper, Every 创始人兼CEO

> "GPT-5.5 比 GPT-5.4 明显更智能、更持久，编码性能更强，工具使用更可靠。它能更长时间保持任务专注，不会过早停止。"
> — Michael Truell, Cursor 联合创始人兼CEO

> "失去 GPT-5.5 访问权限感觉像是被截肢了一样。"
> — NVIDIA 工程师 (早期访问测试者)

### 4.2 知识工作

- 85%+ 的 OpenAI 员工每周使用 Codex
- **财务用例：** 审核 24,771 份 K-1 税表 (71,637 页) — 相比上年节省2周时间
- 生成文档、电子表格、幻灯片
- 自动化商业报告 (每周节省5-10小时)
- OSWorld-Verified: 78.7% 计算机操作能力

### 4.3 科学研究

- **GeneBench：** 25.0% 多阶段基因分析
- **BixBench：** 80.5% 生物信息学基准
- **数学发现：** 在 Lean 中发现并验证了关于 Ramsey 数的新证明
- 作为"研究伙伴"用于评论手稿、压力测试论点、提出分析

---

## 五、推理效率

- **联合设计与训练：** 基于 NVIDIA GB200 和 GB300 NVL72 系统
- 保持与 GPT-5.4 相同的每 token 延迟
- 自定义负载均衡启发式算法使 token 生成速度提升 **20%+**
- 使用 GPT-5.5 改进其自身的服务基础设施

---

## 六、网络安全安全保障

** Preparedness 级别：** 高 (依据 Preparedness Framework)

### 已部署保障措施

1. **更严格的分类器** — 针对潜在网络风险
2. **更高风险活动的更严格控制**
3. **扩展访问** — 通过 Trusted Access for Cyber
4. **网络许可模型的认证要求**

### 访问层级

| 访问级别 | 要求 |
|----------|------|
| **标准 GPT-5.5** | 默认 ChatGPT 访问，含网络分类器 |
| **Trusted Access** | 通过 chatgpt.com/cyber 满足信任信号的已验证用户 |
| **关键基础设施** | 防御关键基础设施的组织 (提供 GPT-5.4-Cyber) |

---

## 七、安全评估流程

GPT-5.5 在发布前进行了全面的安全测试：

| 评估类型 | 描述 |
|----------|------|
| **发布前安全评估** | 完整的内部评估套件 |
| **Preparedness Framework** | 结构化风险评估框架 |
| **红队测试** | 针对高级网络安全和生物能力的定向测试 |
| **早期访问反馈** | 来自近200家早期访问合作伙伴的输入 |

- 发布了"迄今为止最强的安全保障措施集"
- 旨在**减少滥用**同时保留**合法、有益的使用**

---

## 八、GPT-5.5 Pro 特别说明

- 与 GPT-5.5 使用相同的底层模型
- 采用**并行测试时计算**的设置
- GPT-5.5 的安全结果通常作为 GPT-5.5 Pro 的强代理
- 当计算设置可能实质性影响风险或安全保障态势时进行独立评估

---

## 九、相关资源

- [完整 System Card (deploymentsafety.openai.com)](https://deploymentsafety.openai.com/gpt-5-5)
- [GPT-5.5 Bio Bug Bounty](https://openai.com/index/gpt-5-5-bio-bug-bounty/) (2026年4月23日)
- [Accelerating the Cyber Defense Ecosystem](https://openai.com/index/accelerating-cyber-defense-ecosystem/) (2026年4月16日)
- [Our Commitment to Community Safety](https://openai.com/index/our-commitment-to-community-safety/) (2026年4月28日)

---

*文档整理时间：2026年4月30日*
