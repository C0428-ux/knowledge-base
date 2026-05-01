# Introducing Advanced Account Security

**来源：** OpenAI | **发布时间：** 2026年4月30日
**链接：** https://openai.com/index/advanced-account-security
**分类：** 平台功能更新（安全）

---

## 核心内容

OpenAI 推出"高级账户安全"（Advanced Account Security）——一项面向高风险用户的**可选安全设置**，针对记者、民选官员、政治异见人士等群体设计。注册后保护同时覆盖 ChatGPT 和 Codex 账户。

### 核心机制

1. **强制要求通行密钥/物理安全密钥**，禁用密码登录，实现抗钓鱼认证
2. **禁用邮件/SMS 恢复**，仅允许备份通行密钥、安全密钥或恢复密钥（这也意味着 OpenAI 客服无法协助找回已注册账户）
3. **缩短会话有效期**，新增登录警报，支持跨设备活跃会话管理
4. **自动排除训练**：注册用户对话不参与模型训练

### Yubico 合作

与 Yubico 合作提供优惠价安全密钥：
- YubiKey C Nano：适合笔记本电脑日常认证
- YubiKey C NFC：跨设备备份密钥

### Trusted Access for Cyber 强制要求

2026年6月1日起，访问最高权限模型的 Trusted Access for Cyber 成员**必须启用高级账户安全**，或由组织证明其 SSO 工作流包含抗钓鱼认证。

---

## 关键要点
- OpenAI 推出可选高级账户安全功能，面向高风险数字攻击用户
- 强制通行密钥认证，禁用密码+邮件/SMS 恢复，零模型训练
- 与 Yubico 合作提供安全密钥优惠，6月1日起部分用户强制启用
- 未来计划扩展至企业环境
