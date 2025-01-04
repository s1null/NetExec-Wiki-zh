---
description: 使用 NetExec 获取远程文件或发送远程文件
---

# 文件上传下载

## 发送文件到远程目标

将本地文件发送到远程目标

```
nxc ssh 172.16.251.152 -u user -p pass --put-file file.txt /tmp/file.txt
```

## 从远程目标获取文件

从远程目标获取远程文件

```
nxc ssh 172.16.251.152 -u user -p pass --get-file /tmp/file.txt file.txt
```
