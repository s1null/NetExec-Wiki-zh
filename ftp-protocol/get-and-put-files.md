---
description: >-
  使用 NetExec 进行 FTP 文件访问和传输的说明。
---

# 🆕 文件上传和下载

## 列出目录中的文件

使用 FTP 列出特定目录中的文件。

```
netexec ftp [IP_ADDRESS] -u [USERNAME] -p [PASSWORD] --ls [DIRECTORY]
```

示例：

```
netexec ftp 10.10.176.246 -u frank -p D2xc9CgD --ls
FTP         10.10.176.246   21     10.10.176.246    [*] Banner: (vsFTPd 3.0.3)
FTP         10.10.176.246   21     10.10.176.246    [+] frank:D2xc9CgD
FTP         10.10.176.246   21     10.10.176.246    [*] Directory Listing
FTP         10.10.176.246   21     10.10.176.246    drwx------   10 1001     1001         4096 Sep 15  2021 Maildir
FTP         10.10.176.246   21     10.10.176.246    -rw-rw-r--    1 1001     1001         4006 Sep 15  2021 README.txt
FTP         10.10.176.246   21     10.10.176.246    -rw-rw-r--    1 1001     1001           39 Sep 15  2021 ftp_flag.thm
```

## 下载文件

从 FTP 服务器下载文件。

```
netexec ftp [IP_ADDRESS] -u [USERNAME] -p [PASSWORD] --get [FILE]
```

示例：

```
netexec ftp 10.10.176.246 -u frank -p D2xc9CgD --get ftp_flag.thm
FTP         10.10.176.246   21     10.10.176.246    [*] Banner: (vsFTPd 3.0.3)
FTP         10.10.176.246   21     10.10.176.246    [+] frank:D2xc9CgD
FTP         10.10.176.246   21     10.10.176.246    [+] Downloaded: ftp_flag.thm
```

## 上传文件

在拥有相关权限的情况下，向 FTP 服务器上传文件

```
netexec ftp [IP_ADDRESS] -u [USERNAME] -p [PASSWORD] --put [LOCAL_FILE] [REMOTE_FILE]
```

示例：

```
netexec ftp 10.10.176.246 -u frank -p D2xc9CgD --put test.txt test.txt
FTP         10.10.176.246   21     10.10.176.246    [*] Banner: (vsFTPd 3.0.3)
FTP         10.10.176.246   21     10.10.176.246    [+] frank:D2xc9CgD
FTP         10.10.176.246   21     10.10.176.246    [-] Failed to upload file. Response: (550 Permission denied.)
```
