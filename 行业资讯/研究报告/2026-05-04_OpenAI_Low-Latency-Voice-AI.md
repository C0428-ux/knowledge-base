# How OpenAI Delivers Low-Latency Voice AI at Scale

**来源：** OpenAI Engineering Blog | **发布时间：** 2026-05-04
**链接：** https://openai.com/index/delivering-low-latency-voice-ai-at-scale
**分类：** 研究报告（工程/基础设施）

---

## 核心内容

OpenAI 详细披露了其语音 AI 的低延迟技术架构，支撑全球 9 亿周活用户。主要技术决策包括：

1. **采用 Transceiver 而非 SFU 模型**：WebRTC 边缘服务终止客户端连接，转换为内部简化协议处理推理、转录和编排，适合 1:1 会话场景
2. **解决 Kubernetes 端口耗尽问题**：传统 WebRTC 每会话占用大量 UDP 端口，与 K8s 自动扩缩容冲突。通过 ICE 用户名片段（ufrag）编码路由元数据，实现首包路由
3. **Relay + Transceiver 分离架构**：Relay 仅做数据包转发（不解密、不运行 ICE 状态机），Transceiver 持有完整 WebRTC 会话状态，监听共享 UDP socket
4. **Redis 缓存加速会话恢复**：Relay 重启后，STUN 数据包从 ufrag 路由提示重建会话，Redis 缓存 `<客户端IP+端口, transceiver IP+端口>` 映射加速恢复

## 关键要点
- WebRTC 的核心价值在于音频作为连续流到达，使 AI 能在用户说话时就开始转录、推理和生成语音
- 通过地理分布的 Relay 集群实现全球低延迟接入，配合 Cloudflare -geo 导向信令到最近 transceiver 集群
- Relay 用 Go 语言编写，设计极简——只解析 STUN 头部读取路由提示，辅助会话重建
- 整体设计使后端服务像普通服务一样扩缩，而非作为 WebRTC 对等节点
