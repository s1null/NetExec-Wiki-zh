# 目录

* [欢迎](README.md)
* [新闻](news/README.md)
  * [🕷️ v1.0.0 发布!](news/v1.0.0-release.md)
  * [🔧 v1.1.0 - nxc4u](news/v1.1.0-nxc4u.md)
  * [📡 v1.2.0 - ItsAlwaysDNS](news/v1.2.0-ItsAlwaysDNS.md)
  * [🏎️ v1.3.0 - NeedForSpeed](news/v1.3.0-NeedForSpeed.md)
* [Logo 和横幅](logo-and-banner.md)
* [更新日志](changelog.md)

## 入门指南

* [安装](getting-started/installation/README.md)
  * [🐧 Unix 系统安装](getting-started/installation/installation-on-unix.md)
  * [🪟 Windows 系统安装](getting-started/installation/installation-on-windows.md)
  * [🍎 Mac 系统安装](getting-started/installation/installation-for-mac.md)
  * [🛠️ 手动编译二进制文件](getting-started/installation/manually-building-the-binary.md)
  * [➡️ 设置 Tab 自动补全](getting-started/installation/setting-up-tab-completion.md)
* [选择和使用协议](getting-started/selecting-and-using-a-protocol.md)
* [目标格式](getting-started/target-formats.md)
* [使用凭证](getting-started/using-credentials.md)
* [使用 Kerberos](getting-started/using-kerberos.md)
* [使用模块](getting-started/using-modules.md)
* [🆕 DNS 选项](getting-started/dns-options.md)
* [数据库基本使用](getting-started/database-general-usage.md)
* [BloodHound 集成](getting-started/bloodhound-integration.md)
* [审计模式](getting-started/audit-mode.md)
* [忽略 OpSec 警告](getting-started/ignore-opsec-warnings.md)
* [日志记录](getting-started/log-your-results.md)

## SMB 协议

* [漏洞扫描](smb-protocol/scan-for-vulnerabilities.md)
* [枚举](smb-protocol/enumeration/README.md)
  * [生成主机文件](smb-protocol/enumeration/generate-hosts-file.md)
  * [枚举主机](smb-protocol/enumeration/enumerate-hosts.md)
  * [枚举空会话](smb-protocol/enumeration/enumerate-null-sessions.md)
  * [枚举访客登录](smb-protocol/enumeration/enumerate-guest-logon.md)
  * [枚举未要求 SMB 签名的主机](smb-protocol/enumeration/smb-signing-not-required.md)
  * [枚举活动会话](smb-protocol/enumeration/enumerate-active-sessions.md)
  * [枚举共享和访问权限](smb-protocol/enumeration/enumerate-shares-and-access.md)
  * [🆕 枚举网络接口](smb-protocol/enumeration/enumerate-network-interfaces.md)
  * [枚举磁盘](smb-protocol/enumeration/enumerate-disks.md)
  * [枚举已登录用户](smb-protocol/enumeration/enumerate-logged-on-users.md)
  * [枚举域用户](smb-protocol/enumeration/enumerate-domain-users.md)
  * [通过暴力破解 RID 枚举用户](smb-protocol/enumeration/enumerate-users-by-bruteforcing-rid.md)
  * [枚举域组](smb-protocol/enumeration/enumerate-domain-groups.md)
  * [枚举本地组](smb-protocol/enumeration/enumerate-local-groups.md)
  * [枚举域密码策略](smb-protocol/enumeration/enumerate-domain-password-policy-1.md)
  * [🆕 枚举防病毒和 EDR](smb-protocol/enumeration/enumerate-antivirus-edr.md)
* [密码喷洒攻击](smb-protocol/password-spraying.md)
* [身份认证](smb-protocol/authentication/README.md)
  * [检查域凭证](smb-protocol/authentication/checking-credentials-domain.md)
  * [检查本地凭证](smb-protocol/authentication/checking-credentials-local.md)
  * [🆕 委派](smb-protocol/authentication/delegation.md)
* [命令执行](smb-protocol/command-execution/README.md)
  * [执行远程命令](smb-protocol/command-execution/execute-remote-command/README.md)
    * [进程注入 (pi 模块)](smb-protocol/command-execution/execute-remote-command/process-injection-pi-module.md)
  * [获取 Shell 基础](smb-protocol/command-execution/getting-shells-101.md)
* [共享遍历](smb-protocol/spidering-shares.md)
* [文件上传下载](smb-protocol/get-and-put-files.md)
* [获取凭证](smb-protocol/obtaining-credentials/README.md)
  * [导出 SAM](smb-protocol/obtaining-credentials/dump-sam.md)
  * [导出 LSA](smb-protocol/obtaining-credentials/dump-lsa.md)
  * [导出 NTDS.dit](smb-protocol/obtaining-credentials/dump-ntds.dit.md)
  * [导出 LSASS](smb-protocol/obtaining-credentials/dump-lsass.md)
  * [导出 DPAPI](smb-protocol/obtaining-credentials/dump-dpapi.md)
  * [🆕 导出 SCCM](smb-protocol/obtaining-credentials/dump-sccm.md)
  * [🆕 导出 Token Broker Cache](smb-protocol/obtaining-credentials/dump-token-broker-cache.md)
  * [导出 WIFI 密码](smb-protocol/obtaining-credentials/dump-wifi-password.md)
  * [导出 KeePass](smb-protocol/obtaining-credentials/dump-keepass.md)
  * [导出 Veeam](smb-protocol/obtaining-credentials/dump-veeam.md)
  * [导出 WinSCP](smb-protocol/obtaining-credentials/dump-winscp.md)
  * [🆕 导出 PuTTY](smb-protocol/obtaining-credentials/dump-putty.md)
  * [🆕 导出 VNC](smb-protocol/obtaining-credentials/dump-vnc.md)
  * [🆕 导出 mRemoteNG](smb-protocol/obtaining-credentials/dump-mremoteng.md)
  * [🆕 导出远程桌面凭证管理器](smb-protocol/obtaining-credentials/dump-rdcman.md)
* [绕过 LAPS](smb-protocol/defeating-laps.md)
* [检查 Spooler 和 WebDav](smb-protocol/spooler-webdav-running.md)
* [窃取 Microsoft Teams Cookies](smb-protocol/steal-microsoft-teams-cookies.md)
* [🆕 模拟已登录用户](smb-protocol/impersonate-logged-on-users.md)
* [🆕 导出用户本地安全问题](smb-protocol/dump-user-local-security-questions.md)

## LDAP 协议

* [身份认证](ldap-protocol/authentication.md)
* [枚举用户](ldap-protocol/enumerate-users.md)
* [枚举组成员](ldap-protocol/enumerate-group-members.md)
* [🆕 查询 LDAP](ldap-protocol/query-ldap.md)
* [ASREPRoast 攻击](ldap-protocol/asreproast.md)
* [查找域 SID](ldap-protocol/find-domain-sid.md)
* [Kerberoasting 攻击](ldap-protocol/kerberoasting.md)
* [🆕 查找错误配置的委派](ldap-protocol/find-misconfigured-delegation.md)
* [非约束委派](ldap-protocol/unconstrained-delegation.md)
* [管理员计数](ldap-protocol/admin-count.md)
* [机器账户配额](ldap-protocol/machine-account-quota.md)
* [获取用户描述](ldap-protocol/get-user-descriptions.md)
* [导出 gMSA](ldap-protocol/dump-gmsa.md)
* [利用 ESC8 (ADCS)](ldap-protocol/exploit-esc8-adcs.md)
* [提取子网](ldap-protocol/extract-subnet.md)
* [检查 LDAP 签名](ldap-protocol/check-ldap-signing.md)
* [读取 DACL 权限](ldap-protocol/read-dacl-right.md)
* [提取 gMSA 密钥](ldap-protocol/extract-gmsa-secrets.md)
* [BloodHound 数据采集](ldap-protocol/bloodhound-ingestor.md)
* [列出域控制器 IP](ldap-protocol/dc-list.md)
* [枚举域信任关系](ldap-protocol/enumerate-trusts.md)
* [🆕 枚举 SCCM](ldap-protocol/enumerate-sccm.md)

## WINRM 协议

* [密码喷洒攻击](winrm-protocol/password-spraying.md)
* [身份认证](winrm-protocol/authentication.md)
* [命令执行](winrm-protocol/command-execution.md)
* [🆕 绕过 LAPS](winrm-protocol/defeating-laps.md)

## MSSQL 协议

* [密码喷洒攻击](mssql-protocol/mssql-passwordspray.md)
* [身份认证](mssql-protocol/authentication.md)
* [MSSQL 权限提升](mssql-protocol/mssql-privesc.md)
* [MSSQL 命令执行](mssql-protocol/mssql-command.md)
* [MSSQL 上传下载](mssql-protocol/mssql-upload-download.md)
* [通过 xp_cmdshell 执行命令](mssql-protocol/windows-command.md)
* [🆕 通过暴力破解 RID 枚举用户](mssql-protocol/enumerate-users-by-bruteforcing-rid.md)

## SSH 协议

* [密码喷洒攻击](ssh-protocol/password-spraying.md)
* [身份认证](ssh-protocol/authentication.md)
* [命令执行](ssh-protocol/command-execution.md)
* [文件上传下载](ssh-protocol/get-and-put-files.md)

## FTP 协议

* [密码喷洒攻击](ftp-protocol/password-spraying.md)
* [🆕 文件列表等](ftp-protocol/file-listing-etc.md)
* [🆕 文件上传下载](ftp-protocol/get-and-put-files.md)

## RDP 协议

* [密码喷洒攻击](rdp-protocol/password-spraying.md)
* [截图 (已连接)](rdp-protocol/screenshot-connected.md)
* [无 NLA 截图 (未连接)](rdp-protocol/screenshot-without-nla-not-connected.md)

## WMI 协议

* [密码喷洒攻击](wmi-protocol/password-spraying.md)
* [身份认证](wmi-protocol/authentication.md)
* [命令执行](wmi-protocol/command-execution.md)

## NFS 协议

* [🆕 枚举](nfs-protocol/Enumeration.md)
* [🆕 文件下载和上传](nfs-protocol/Download-and-Upload-Files.md)
