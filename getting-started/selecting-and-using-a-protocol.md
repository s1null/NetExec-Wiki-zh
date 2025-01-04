---
description: 在 NetExec 中选择和使用协议
---

# 选择和使用协议

## 可用协议

<pre><code><strong>smb
</strong><strong>ssh
</strong><strong>ldap
</strong><strong>ftp
</strong><strong>wmi
</strong><strong>winrm
</strong><strong>rdp
</strong><strong>vnc
</strong><strong>mssql
</strong><strong>nfs
</strong></code></pre>

注意不是所有协议都支持相同的功能,请务必检查每个协议的选项

## 使用协议选项

要查看协议的选项,运行: `nxc <protocol> --help`

然后使用这些选项: `nxc <protocol> <protocol options>`

## 查看可用协议

运行 `nxc --help` 将列出一般选项和可用的协议(注意下面的 'protocols' 部分):

```
#~ nxc --help
usage: nxc [-h] [-t THREADS] [--timeout TIMEOUT] [--jitter INTERVAL] [--no-progress] [--verbose] [--debug] [--version] {smb,ssh,ldap,ftp,wmi,winrm,rdp,vnc,mssql} ...

    <-- Banner -->   

options:
  -h, --help            显示此帮助消息并退出
  -t THREADS           设置要使用的并发线程数(默认: 100)
  --timeout TIMEOUT     每个线程的最大超时时间(秒)(默认: None)
  --jitter INTERVAL     在每个连接之间设置随机延迟(默认: None)
  --no-progress        扫描期间不显示进度条
  --verbose            启用详细输出
  --debug              启用调试级别信息
  --version            显示 nxc 版本

protocols:
  可用协议

  {smb,ssh,ldap,ftp,wmi,winrm,rdp,vnc,mssql,nfs}
    smb                 使用 SMB 获取权限
    ssh                 使用 SSH 获取权限
    ldap                使用 LDAP 获取权限
    ftp                 使用 FTP 获取权限
    wmi                 使用 WMI 获取权限
    winrm               使用 WINRM 获取权限
    rdp                 使用 RDP 获取权限
    vnc                 使用 VNC 获取权限
    mssql               使用 MSSQL 获取权限
    nfs                 使用 NFS 获取权限
```
