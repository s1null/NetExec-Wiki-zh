# 检查本地凭证

### 用户名/密码/哈希

在任何身份认证命令中添加 `--local-auth` 参数将尝试本地登录。

```
#~ nxc smb 192.168.1.0/24 -u UserNAme -p 'PASSWORDHERE' --local-auth
#~ nxc smb 192.168.1.0/24 -u '' -p '' --local-auth
#~ nxc smb 192.168.1.0/24 -u UserNAme -H 'LM:NT' --local-auth
#~ nxc smb 192.168.1.0/24 -u UserNAme -H 'NTHASH' --local-auth
#~ nxc smb 192.168.1.0/24 -u localguy -H '13b29964cc2480b4ef454c59562e675c' --local-auth
#~ nxc smb 192.168.1.0/24 -u localguy -H 'aad3b435b51404eeaad3b435b51404ee:13b29964cc2480b4ef454c59562e675c' --local-auth
```

结果将在用户名:密码旁边显示主机名

```
	SMB         192.168.1.101    445    HOSTNAME          [+] HOSTNAME\Username:Password (Pwn3d!)  
```
