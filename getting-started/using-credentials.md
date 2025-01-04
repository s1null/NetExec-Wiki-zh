---
description: 在 NetExec 中使用凭证
---

# 使用凭证

## 使用凭证

每个协议都以某种形式支持使用凭证。有关使用特定协议的凭证的详细信息,请参阅相应的 wiki 部分。

一般来说,要使用凭证,你可以运行以下命令:

```
netexec <protocol> <target(s)> -u username -p password
```

{% hint style="success" %}
代码执行会在登录确认后添加 (**Pwn3d!**)。对于 SMB 协议,很可能你的已破解用户在本地管理员组中。
{% endhint %}

| 协议 | 输出中看到 Pwn3d!                                   |
| -------- | ------------------------------------------------------ |
| FTP      | 无检查                                               |
| SSH      | root (否则特定消息) :white_check_mark: |
| WINRM    | 至少代码执行 :space_invader:               |
| LDAP     | 通向域管理员的路径 :crown:                           |
| SMB      | 很可能是本地管理员 :white_check_mark:           |
| RDP      | 至少代码执行 :space_invader:               |
| VNC      | 至少代码执行 :space_invader:               |
| WMI      | 很可能是本地管理员 :white_check_mark:           |

{% hint style="info" %}
当使用包含特殊符号的用户名或密码时,请用单引号将它们括起来,以便你的 shell 将它们解释为字符串。
{% endhint %}

Example:

```
netexec <protocol> <target(s)> -u username -p 'October2022!'
```

{% hint style="info" %}
由于 Python 的参数解析库存在 [bug](https://bugs.python.org/issue9334),以单引号开头或包含特殊符号的凭证可能会抛出 `expected at least one argument` 错误消息。为了绕过这个问题,请使用 'long' 参数格式(注意 `=` 符号):
{% endhint %}

```
netexec <protocol> <target(s)> -u='-username' -p='-October2022'
```

## 使用数据库中的凭证集

通过指定凭证 ID (或多个凭证 ID) 使用 `-id` 标志 nxc 将自动从后端数据库中提取该凭证并使用它进行身份验证 (节省大量输入):

```
netexec <protocol> <target(s)> -id <cred ID(s)>
```

## 多域环境

你可以使用 nxc 与多个域环境

```
netexec <protocol> <target(s)> -u FILE -p password
```

其中 **FILE** 是一个包含以下格式的用户名文件

```
DOMAIN1\user
DOMAIN2\user
```

## 暴力破解和密码喷射

所有协议都支持暴力破解和密码喷射。有关使用特定协议的暴力破解/密码喷射的详细信息,请参阅相应的 wiki 部分。

通过指定文件或多个值 nxc 将自动暴力破解所有目标使用指定协议的登录:

Examples:

```
netexec <protocol> <target(s)> -u username1 -p password1 password2
```

```
netexec <protocol> <target(s)> -u username1 username2 -p password1
```

```
netexec <protocol> <target(s)> -u ~/file_containing_usernames -p ~/file_containing_passwords
```

```
netexec <protocol> <target(s)> -u ~/file_containing_usernames -H ~/file_containing_ntlm_hashes
```

## 密码喷射而不使用暴力破解

对于 WinRM 和 MSSQL 等协议,此选项避免使用文件 (-u file -p file) 的暴力破解。

```
netexec <protocol> <target(s)> -u ~/file_containing_usernames -H ~/file_containing_ntlm_hashes --no-bruteforce
```

```
netexec <protocol> <target(s)> -u ~/file_containing_usernames -p ~/file_containing_passwords --no-bruteforce
```

```
user1 -> pass1
user2 -> pass2
```

{% hint style="info" %}
默认情况下,nxc 会在找到有效的登录后退出。使用 `--continue-on-success` 标志将连续喷射,即使找到有效的密码。此标志与命令执行不兼容。
{% endhint %}

```
netexec <protocol> <target(s)> -u ~/file_containing_usernames -H ~/file_containing_ntlm_hashes --no-bruteforce --continue-on-success
```

### 限制认证请求

{% hint style="warning" %}
认证限制工作在每个主机的基础上!请记住,如果你正在向多个主机喷射凭证,请保持此点。
{% endhint %}

如果需要限制在暴力破解期间进行认证,可以使用 jitter 功能。请求之间的超时时间 (以秒为单位) 是从间隔中随机选择的,除非另有指定。如果你想硬编码超时,请将间隔的上限和下限设置为相同的值。语法如下:

```
netexec --jitter 3 <protocol> <target> -u ~/file_containing_usernames -p ~/file_containing_passwords
netexec --jitter 2-5 <protocol> <target> -u ~/file_containing_usernames -p ~/file_containing_passwords
netexec --jitter 4-4 <protocol> <target> -u ~/file_containing_usernames -p ~/file_containing_passwords
```
