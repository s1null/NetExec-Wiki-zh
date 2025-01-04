# 无约束委派

NetExec 允许你获取所有带有 **TRUSTED_FOR_DELEGATION** 标志的计算机和用户列表

```
nxc ldap 192.168.0.104 -u harry -p pass --trusted-for-delegation
```

### 替代工具

{% embed url="https://github.com/ropnop/windapsearch" %}

{% embed url="https://github.com/PowerShellMafia/PowerSploit/blob/dev/Recon/PowerView.ps1" %}

### 资源:

{% embed url="https://troopers.de/downloads/troopers19/TROOPERS19_AD_Fun_With_LDAP.pdf" %}

{% embed url="https://beta.hackndo.com/unconstrained-delegation-attack/" %}

{% embed url="https://dirkjanm.io/krbrelayx-unconstrained-delegation-abuse-toolkit/" %}

{% embed url="https://posts.specterops.io/hunting-in-active-directory-unconstrained-delegation-forests-trusts-71f2b33688e1" %}
