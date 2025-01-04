# 获取用户描述

新的 LDAP 模块用于在用户描述中查找密码。

```
nxc ldap <hostname> -u <user> -p <pass> -M get-desc-users
```

有三个可用选项:

* **FILTER**: 在描述中查找字符串
* **PASSWORDPOLICY**: 根据 Windows 的复杂性要求查找密码
* **MINLENGTH**: 选择密码的最小长度(可以从 `--pass-pol` 获取)
