---
description: 导出存储的认证私钥或存储的代理凭证
---

# 🆕 导出 PuTTY

{% hint style="warning" %}
你需要在远程目标上至少具有本地管理员权限，如果你的用户是本地账户，请使用 **--local-auth** 选项
{% endhint %}

PuTTY 允许用户存储连接的私钥。它还允许在配置中设置每个连接的代理凭证，这些凭证会以明文形式存储在注册表中。此模块将自动在 PuTTY 注册表路径中查找这些属性，如果找到则提取它们。

```
nxc smb 192.168.56.11 -u eddard.stark -p FightP3aceAndHonor! -M putty
```
