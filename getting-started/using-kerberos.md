---
description: 在 NetExec 中使用 Kerberos 认证
---

# 使用 Kerberos

## 使用 Kerberos

nxc 支持 Kerberos 认证。有两个选项,直接使用密码/哈希或使用票据并使用 `KRB5CCNAME` 环境变量来指定票据。

{% hint style="info" %}
当使用 `-k` 或 `--use-kcache` 选项时,你需要指定与 kerberos 票据中相同的主机名(FQDN)
{% endhint %}

```
$ sudo nxc smb zoro.gold.local -k -u bonclay -p Ocotober2022
SMB         zoro.gold.local 445    ZORO             [*] Windows 10.0 Build 14393 (name:ZORO) (domain:gold.local) (signing:False) (SMBv1:False)
SMB         zoro.gold.local 445    ZORO             [+] gold.local\bonclay
```

或者,使用 `--use-kcache`

```
$ export KRB5CCNAME=/home/bonclay/impacket/administrator.ccache 
$ nxc smb zoro.gold.local --use-kcache
SMB         zoro.gold.local 445    ZORO             [*] Windows 10.0 Build 14393 (name:ZORO) (domain:gold.local) (signing:False) (SMBv1:False)
SMB         zoro.gold.local 445    ZORO             [+] gold.local\administrator (Pwn3d!)
$ sudo nxc smb zoro.gold.local --use-kcache -x whoami
SMB         zoro.gold.local 445    ZORO             [*] Windows 10.0 Build 14393 (name:ZORO) (domain:gold.local) (signing:False) (SMBv1:False)
SMB         zoro.gold.local 445    ZORO             [+] gold.local\administrator (Pwn3d!)
SMB         zoro.gold.local 445    ZORO             [+] Executed command 
SMB         zoro.gold.local 445    ZORO             gold\administrator

$ export KRB5CCNAME=/home/bonclay/impacket/bonclay.ccache
$ sudo nxc smb zoro.gold.local --use-kcache -x whoami
SMB         zoro.gold.local 445    ZORO             [*] Windows 10.0 Build 14393 (name:ZORO) (domain:gold.local) (signing:False) (SMBv1:False)
SMB         zoro.gold.local 445    ZORO             [+] gold.local\bonclay
```

使用 LDAP 和 `--kdcHost` 选项的示例

```
poetry run NetExec ldap poudlard.wizard -k --kdcHost dc01.poudlard.wizard 
SMB poudlard.wizard 445 DC01 [*] Windows 10.0 Build 17763 x64 (name:DC01) (domain:poudlard.wizard) (signing:True) (SMBv1:False) 
LDAP poudlard.wizard 389 DC01 [+] poudlard.wizard\
```
