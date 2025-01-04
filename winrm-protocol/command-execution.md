# 命令执行

使用 WinRM 执行命令

```
#~ nxc winrm 192.168.255.131 -u user -p 'password' -X whoami
WINRM       192.168.255.131 5985   ROGER            [*] http://192.168.255.131:5985/wsman
WINRM       192.168.255.131 5985   ROGER            [+] GOLD\user:password (Pwn3d!)
WINRM       192.168.255.131 5985   ROGER            [+] Executed command
WINRM       192.168.255.131 5985   ROGER            gold\user
```

## 下一步？

使用 Evil-winrm 工具来掌控一切！

{% embed url="https://github.com/Hackplayers/evil-winrm" %}
