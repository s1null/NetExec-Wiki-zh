---
description: 使用 NetExec 执行 MSSQL 命令
---

# MSSQL 命令

### 执行 MSSQL 命令

```
nxc mssql 10.10.10.52 -u admin -p 'm$$ql_S@_P@ssW0rd!' --local-auth -q 'SELECT name FROM master.dbo.sysdatabases;'
```

预期结果:

```
MSSQL       10.10.10.52     1433   None             [+] admin:m$$ql_S@_P@ssW0rd! (Pwn3d!)
MSSQL       10.10.10.52     1433   None             name
MSSQL       10.10.10.52     1433   None             --------------------------------------------------------------------------------------------------------------------------------
MSSQL       10.10.10.52     1433   None             master
MSSQL       10.10.10.52     1433   None             tempdb
MSSQL       10.10.10.52     1433   None             model
MSSQL       10.10.10.52     1433   None             msdb
MSSQL       10.10.10.52     1433   None             orcharddb
```

{% hint style="info" %}
在使用 MSSQL 时,你可以使用 [quentinhardy](https://github.com/quentinhardy) 开发的工具 [MSDAT](https://github.com/quentinhardy/msdat)
{% endhint %}

{% embed url="https://github.com/quentinhardy/msdat" %}

### 示例

Mantis 机器是使用 NetExec 测试 **MSSQL** 协议的一个很好的例子

{% embed url="https://www.hackthebox.eu/home/machines/profile/98" %}
