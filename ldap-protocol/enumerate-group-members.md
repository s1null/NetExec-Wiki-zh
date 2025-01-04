# 枚举组成员

通过 LDAP 枚举特定组中的所有成员:

```
nxc ldap $ip -u $user -p $password -M group-mem -o GROUP="Domain Admins"
```
