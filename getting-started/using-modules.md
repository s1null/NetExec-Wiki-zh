---
description: 在 NetExec 中使用模块
---

# 使用模块

## 使用模块

### 查看协议可用的模块

运行 `nxc <protocol> -L` 查看指定协议的可用模块。

例如查看 SMB 协议的所有模块:

```
nxc smb -L
```

### 使用模块

运行 `nxc <protocol> <target(s)> -M <module name>`。

例如运行 SMB Mimikatz 模块:

```
nxc smb <target(s)> -u Administrator -p 'October2022' -M lsassy
```

### 查看模块选项

运行 `nxc <protocol> -M <module name> --options` 查看模块支持的选项,例如:

```
nxc smb -M lsassy --options
```

### 使用模块选项

模块选项使用 `-o` 标志指定。所有选项都以 KEY=value 的形式指定(msfvenom 风格)

示例:

```
nxc <protocol> <target(s)> -u Administrator -p 'P@ssw0rd' -M lsassy -o COMMAND=xxxxxxxxug'
```

### 🆕 运行多个模块

只需定义你想要的所有模块,每个模块前面都有 `-M` 选项标志:

`nxc <protocol> <target(s)> -u Administrator -p 'P@ssw0rd' -M spooler -M printnightmare -M shadowcoerce -M petitpotam`
