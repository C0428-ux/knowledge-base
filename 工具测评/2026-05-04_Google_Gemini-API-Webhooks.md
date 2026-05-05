# Reduce friction and latency for long-running jobs with Webhooks in Gemini API

**来源：** Google Blog | **发布时间：** 2026-05-04
**链接：** https://blog.google/innovation-and-ai/technology/developers-tools/event-driven-webhooks/
**分类：** 平台功能更新

---

## 核心内容

Google 宣布在 Gemini API 中推出事件驱动的 Webhooks，为长时运行的 agentic 应用提供实时推送通知，替代低效的轮询模式。

### 技术实现

- **推送机制**：任务完成时，Gemini API 主动向开发者服务器发送 HTTP POST payload
- **安全设计**：严格遵循 Standard Webhooks 规范，使用 `webhook-signature`、`webhook-id`、`webhook-timestamp` 头部签名，确保幂等性和防重放攻击
- **可靠性保证**：「至少一次」交付，自动重试最长 24 小时
- **配置灵活性**：支持项目级全局配置（HMAC 加密）和单次请求级动态覆盖（JWKS 加密）

### 适用场景

- Deep Research（深度研究）
- 长视频生成
- Batch API 处理数千个 prompt（可能耗时数分钟至数小时）

## 关键要点
- Webhooks 替代轮询，显著降低延迟和资源消耗
- 遵循 Standard Webhooks 规范，安全性有保障
- Python SDK 已支持快速配置示例
- 现已对所有 Gemini API 开发者开放
