---
description: ldapsearch 的替代方案
---

# 🆕 查询 LDAP

如果你需要查询原始 ldap 值,你可以使用查询选项和过滤器。返回的值不会以任何方式解析,应该返回与 ldapsearch 或类似工具完全相同的输出。

```
nxc ldap <ip> -u username -p password --query "(sAMAccountName=Administrator)" ""
nxc ldap <ip> -u username -p password --query "(sAMAccountName=Administrator)" "sAMAccountName objectClass pwdLastSet"
```

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption><p>使用 NetExec 查询 ldap</p></figcaption></figure>
