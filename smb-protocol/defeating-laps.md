---
description: NetExec vs LAPS
---

# 绕过 LAPS

### 在域中安装了 LAPS 时使用 NetExec

如果域中使用了 LAPS，使用 NetExec 在域中的每台计算机上执行命令可能会很困难。

因此，添加了一个新的核心选项 `--laps`！如果你已经攻破了一个可以读取 LAPS 密码的账户，你可以这样使用 NetExec：

nxc `smb <ip> -u user-can-read-laps -p pass --laps`

{% hint style="info" %}
如果默认管理员名称不是 `administrator`，在选项后添加用户名

`--laps name`
{% endhint %}
