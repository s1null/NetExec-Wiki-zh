# 枚举未要求 SMB 签名的主机

映射活动主机网络并保存一个仅包含**不**要求 SMB 签名的主机列表。\
列表格式为每行一个 IP

```
nxc smb 192.168.1.0/24 --gen-relay-list relay_list.txt
```

预期结果：

```
SMB         192.168.1.101    445    DC2012A          [*] Windows Server 2012 R2 Standard 9600 x64 (name:DC2012A) (domain:OCEAN) (signing:True) (SMBv1:True)
SMB         192.168.1.102    445    DC2012B          [*] Windows Server 2012 R2 Standard 9600 x64 (name:DC2012B) (domain:EARTH) (signing:True) (SMBv1:True)
SMB         192.168.1.111    445    SERVER1          [*] Windows Server 2016 Standard Evaluation 14393 x64 (name:SERVER1) (domain:PACIFIC) (signing:False) (SMBv1:True)
SMB         192.168.1.117    445    WIN10DESK1       [*] WIN10DESK1 x64 (name:WIN10DESK1) (domain:OCEAN) (signing:False) (SMBv1:True)
...SNIP...

#~ cat relay_list.txt
192.168.1.111
192.168.1.117
```

### 使用 nmap 的替代方法

你也可以使用 nmap 列出**不**要求 SMB 签名的主机

```
nmap --script smb-security-mode.nse,smb2-security-mode.nse -p445 127.0.0.1
```
