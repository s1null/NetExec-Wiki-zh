# 身份认证

### WinRM 身份认证

#### 测试凭证

```
#~ nxc winrm 192.168.1.0/24 -u user -p password
```

预期结果：

```
WINRM       192.168.255.131 5985   ROGER            [*] http://192.168.255.131:5985/wsman
WINRM       192.168.255.131 5985   ROGER            [+] GOLD\user:password (Pwn3d!)
```

如果 SMB 端口关闭，你也可以使用 `-d DOMAIN` 标志来避免 SMB 连接

```
#~ nxc winrm 192.168.1.0/24 -u user -p password -d DOMAIN
```

预期结果：

```
WINRM       192.168.255.131 5985   192.168.255.131  [*] http://192.168.255.131:5985/wsman
WINRM       192.168.255.131 5985   192.168.255.131  [+] GOLD\user:password (Pwn3d!)
```

### 示例

Monteverde 机器是使用 NetExec 测试 **WinRM** 协议的一个很好的例子

{% embed url="https://www.hackthebox.eu/home/machines/profile/223" %}
