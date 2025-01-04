# 密码喷洒攻击

### 密码喷洒攻击（不使用暴力破解）

```
#~ nxc ssh 192.168.1.0/24 -u userfile -p passwordfile --no-bruteforce
```

预期结果：

```
SSH         127.0.0.1       22     127.0.0.1        [*] SSH-2.0-OpenSSH_8.2p1 Debian-4
SSH         127.0.0.1       22     127.0.0.1        [+] user:password
```

{% hint style="info" %}
默认情况下，nxc 会在找到一个有效登录后退出。使用 `--continue-on-success` 标志会在找到有效密码后继续喷洒。这在对大量用户列表使用单个密码进行喷洒时很有用。
{% endhint %}

你也可以使用 Kali 默认提供的 [Hydra](https://github.com/vanhauser-thc/thc-hydra) 来暴力破解 SSH 密码，它更快更好 :)

{% embed url="https://github.com/vanhauser-thc/thc-hydra" %}
