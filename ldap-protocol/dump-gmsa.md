---
description: 提取 gmsa 凭证账户
---

# 导出 gMSA

使用 LDAP 协议,如果你有权限,可以提取 gMSA 账户的密码。

{% hint style="warning" %}
需要 LDAPS 来获取密码,使用 --gmsa 时会自动选择 LDAPS
{% endhint %}

```
$ nxc ldap <ip> -u <user> -p <pass> --gmsa
```
