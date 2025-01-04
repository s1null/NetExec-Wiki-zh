# 枚举空会话

检查**空会话**（也称为匿名会话）是否在网络上启用。在域控制器上可以非常有用，用于枚举用户、组、密码策略等。

```
nxc smb 10.10.10.161 -u '' -p ''
nxc smb 10.10.10.161 -u '' -p '' --shares
nxc smb 10.10.10.161 -u '' -p '' --pass-pol
nxc smb 10.10.10.161 -u '' -p '' --users
nxc smb 10.10.10.161 -u '' -p '' --groups
```

你也可以使用 `smbclient` 或 `rpcclient` 复现这种行为

```
smbclient -N -U "" -L \\10.10.10.161
```

```
rpcclient -N -U "" -L \\10.10.10.161
rpcclient $> enumdomusers
user:[bonclay] rid:[0x46e]
user:[zoro] rid:[0x46f]
```

{% embed url="https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/jj852200(v=ws.11)" %}

### 示例

Forest 或 Monteverde 机器是使用 NetExec 测试**空会话**认证的好例子

{% embed url="https://www.hackthebox.eu/home/machines/profile/212" %}

{% embed url="https://www.hackthebox.eu/home/machines/profile/223" %}


