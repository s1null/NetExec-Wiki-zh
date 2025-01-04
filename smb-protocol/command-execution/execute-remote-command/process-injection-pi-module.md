# 进程注入 (pi 模块)

{% hint style="warning" %} 你需要在远程目标上至少具有本地管理员权限 {% endhint %}

"pi" 模块使用进程注入方法访问 Windows 系统上具有活动会话的用户进程，以目标用户的权限执行命令（需要 SYSTEM 权限）。

它允许在 Active Directory 中模拟授权的域用户。

它在 Server 2016/Win10 及以上版本运行更稳定。

```
#~ NetExec <IP> -u username -p password -M pi -o PID=<target_process_pid> EXEC=<command>
```

关于 `pi` 模块的创建的更多信息，请参见开发者的博客文章：[https://medium.com/@mehmetcantopal/development-and-implementation-of-the-pi-smb-module-for-netexec-crackmapexec-83eac92ded8f](https://medium.com/@mehmetcantopal/development-and-implementation-of-the-pi-smb-module-for-netexec-crackmapexec-83eac92ded8f)
