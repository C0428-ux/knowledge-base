# Our Eighth Generation TPUs: Two Chips for the Agentic Era

**来源：** Google Cloud Blog | **发布时间：** Google Cloud Next 2026 (4月)
**链接：** https://blog.google/innovation-and-ai/infrastructure-and-cloud/google-cloud/eighth-generation-tpu-agentic-era/
**分类：** AI产品发布

---

## 核心内容

Google在Cloud Next 2026大会上发布了第八代张量处理单元（TPU），首次推出两款专用芯片：
- **TPU 8t (Sunfish)**：训练芯片，Broadcom设计，TSMC 2nm工艺
- **TPU 8i (Zebrafish)**：推理芯片，MediaTek设计，TSMC 2nm工艺

这是Google首次针对训练和推理分别设计专用TPU芯片，标志着TPU发展史上的重要转折。

---

## 关键要点

1. **TPU 8t 超级Pod规模惊人**：9,600颗芯片组成单一超级Pod，提供2PB共享内存和121 ExaFlops算力，互联带宽是上代Ironwood的2倍

2. **推理效率大幅提升**：TPU 8i实现80%的每美元性能提升，288GB HBM + 384MB SRAM（是上代3倍）消除"内存墙"瓶颈，延迟降低最高5倍

3. **为AI Agent时代设计**：Boardfly网络拓扑减少50%以上网络直径，CAE（Collectives Acceleration Engine）加速全局运算，专门针对Agent连续推理和执行循环场景优化

4. **能效比显著提升**：每瓦性能比Ironwood提升2倍，5年内每单位电力算力提升6倍，暗示算力瓶颈正从芯片供应转向电力供应

5. **Anthropic成为锚定客户**：Anthropic扩展至2027年3.5吉瓦算力协议，成为TPU 8t和Ironwood两代产品的最大客户

---

## 关键规格对比

| 指标 | TPU 8t (训练) | TPU 8i (推理) |
|------|--------------|--------------|
| 工艺 | TSMC 2nm | TSMC 2nm |
| 超级Pod规模 | 9,600芯片 | — |
| 共享内存 | 2 PB | 288 GB HBM |
| 片上SRAM | — | 384 MB |
| 互联带宽 | 2x Ironwood | 19.2 Tb/s |
| 每美元性能 | — | vs Ironwood提升80% |

---

## 战略意义

Google此次发布清晰表明：AI基础设施竞争正从芯片性能转向"全栈优化"——从硅片到数据中心到软件框架的协同设计。随着推理成为Agent时代的主要工作负载，专用推理芯片将成为下一阶段竞争焦点。
