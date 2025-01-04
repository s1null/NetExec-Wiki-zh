# 密码喷洒攻击

### 密码喷洒攻击（不使用暴力破解）

```
#~ nxc ftp 192.168.1.0/24 -u userfile -p passwordfile --no-bruteforce
```

默认情况下，nxc 会在找到一个有效登录后退出。使用 `--continue-on-success` 参数可以在找到有效密码后继续喷洒攻击。这在对大量用户列表使用单个密码进行喷洒时很有用。
