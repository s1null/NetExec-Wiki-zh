# 枚举用户

通过 LDAP 枚举所有用户:

```
nxc ldap $ip -u $user -p $password --users
```

通过 LDAP 仅枚举**活动**用户:

```
nxc ldap $ip -u $user -p $password --active-users
```

查看 @TeRMaN (Mehmetcan Topal) 的博文了解具体差异和实现原因: [https://medium.com/@mehmetcantopal/why-and-how-did-i-implement-an-active-users-ldap-feature-on-netexec-f5c7eff2cb79](https://medium.com/@mehmetcantopal/why-and-how-did-i-implement-an-active-users-ldap-feature-on-netexec-f5c7eff2cb79)
