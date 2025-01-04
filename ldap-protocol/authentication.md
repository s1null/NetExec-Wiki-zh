# 身份认证

### LDAP 身份认证

在不使用 kerberos 协议的情况下测试账户是否存在

```
nxc ldap 192.168.1.0/24 -u users.txt -p '' -k
```

#### 测试凭证

```
nxc ldap 192.168.1.0/24 -u user -p password
```

```
nxc ldap 192.168.1.0/24 -u user -H A29F7623FD11550DEF0192DE9246F46B
```

预期结果:

```
LDAP        192.168.255.131 5985   ROGER            [+] GOLD\user:password
```

{% hint style="warning" %}
需要域名解析
{% endhint %}

默认情况下,ldap 协议会通过连接到 SMB 共享(dc 的)来获取域名,如果你不想要这个初始连接,只需添加 `--no-smb` 选项
