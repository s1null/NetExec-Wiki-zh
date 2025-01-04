---
description: 使用 NetExec 遍历共享
---

# 遍历共享

## 使用默认选项 `--spider`

用于遍历远程系统共享的选项。例如，遍历 C 盘查找名称中包含 txt 的文件（可以找到 sometxtfile.html 和 somefile.txt）

注意 '$' 字符必须转义。（示例可以直接在 kali linux 终端中使用）

```
nxc SMB <IP> -u USER -p PASSWORD --spider C\$ --pattern txt
```

## 使用 "spider_plus" 模块

感谢 [@vincd](https://github.com/vincd)，`spider_plus` 模块允许你列出和导出所有可读共享中的所有文件

### 列出所有可读文件

```
nxc smb 10.10.10.10 -u 'user' -p 'pass' -M spider_plus
```

### 导出所有文件

使用选项 `-o DOWNLOAD_FLAG=True` 将所有文件复制到主机上

```
nxc smb 10.10.10.10 -u 'user' -p 'pass' -M spider_plus -o DOWNLOAD_FLAG=True
```
