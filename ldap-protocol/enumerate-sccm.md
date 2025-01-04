# 🆕 枚举 SCCM

System Center Configuration Manager (SCCM) 或现在也称为 MECM 是一个用于资产/终端管理的管理基础设施。由于它包含许多不同的服务器或应用程序,枚举和映射它们并不容易。

此模块实现了 [Misconfiguration-Manager](https://github.com/subat0mik/Misconfiguration-Manager) 的 LDAP 枚举部分([RECON-1](https://github.com/subat0mik/Misconfiguration-Manager/blob/main/attack-techniques/RECON/RECON-1/recon-1_description.md))来协助在 AD 环境中初步发现 SCCM 实体。它将找到 SCCM Site-Servers、SCCM Sites、SCCM Management Points 以及与 SCCM 相关的用户、计算机或组。

```
nxc ldap 192.168.33.10 u alice -p whiteRabbit -M sccm -o REC_RESOLVE=TRUE
```

<figure><img src="../.gitbook/assets/image (10).png" alt=""><figcaption><p>使用 LDAP 和 SCCM 模块在 Active Directory 中枚举 SCCM 环境</p></figcaption></figure>

{% content-ref url="../smb-protocol/obtaining-credentials/dump-sccm.md" %}
[dump-sccm.md](../smb-protocol/obtaining-credentials/dump-sccm.md)
{% endcontent-ref %}

{% embed url="https://github.com/subat0mik/Misconfiguration-Manager" %}

{% embed url="https://github.com/garrettfoster13/sccmhunter" %}
