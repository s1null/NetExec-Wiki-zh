---
description: 在 NetExec 中使用证书进行身份认证
---

# 使用证书

```
netexec smb 192.168.0.1 --pfx-cert user.pfx -u user 
```

```
netexec smb 192.168.0.1 --pfx-cert user.pfx --pfx-pass password -u user 
```

```
netexec smb 192.168.0.1 --pfx-base64 user.pfx -u user 
```

```
netexec smb 192.168.0.1 --pem-cert user.pem --pem-key key.pem -u user 
```

{% hint style="info" %}
当使用证书进行身份验证时，nxc 会在 nxc 主目录中生成一个 ccache 文件，您也可以使用这个 ccache 文件为其他工具进行 kerberos 身份验证
{% endhint %}