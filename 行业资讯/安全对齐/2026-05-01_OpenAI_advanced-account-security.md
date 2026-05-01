# Introducing Advanced Account Security

**来源：** OpenAI | **发布时间：** 2026-04-30
**链接：** https://openai.com/index/advanced-account-security
**分类：** 安全对齐

---

## 核心内容

OpenAI 推出「Advanced Account Security」可选安全设置，面向数字攻击风险增加的群体（记者、民选官员、政治异见人士、研究人员、安全意识用户）。注册后保护覆盖 ChatGPT 和 Codex 账户，2026年6月1日起访问大部分网络相关模型的用户强制启用。

核心功能：
- 强登录方式：强制使用 Passkey 或实体安全钥匙，禁止密码登录
- 安全账户恢复：禁用邮箱/SMS 恢复，需使用备份 Passkey、安全钥匙和恢复密钥；OpenAI 支持团队无法协助已注册用户恢复账户
- 会话管理：缩短登录会话时长，账户访问时发送警报通知
- 自动训练排除：已注册用户对话自动排除模型训练

合作方：与 Yubico 合作提供优惠定价的物理安全钥匙套装

## 关键要点
- 面向高风险用户群体的钓鱼抵抗认证系统，以 Passkey/FIDO 为核心
- 2026年6月1日起「Trusted Access for Cyber」要求个人用户必须启用
- 企业可使用 SSO 工作流中的钓鱼抵抗认证作为替代方案
- 注册用户的对话默认不参与模型训练（此前需手动选择退出）
