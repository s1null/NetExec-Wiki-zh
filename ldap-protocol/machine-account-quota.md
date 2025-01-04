# 机器账户配额

此模块获取域级别的 MachineAccountQuota 属性。检查这个值很有用,因为默认情况下它允许非特权用户将最多 10 台计算机加入到 Active Directory (AD) 域中。

```
nxc ldap <ip> -u user -p pass -M maq
```
