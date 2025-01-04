# 身份认证

#### 测试凭证

```
#~ nxc ssh 192.168.1.0/24 -u user -p password
```

预期结果：

```
SSH         127.0.0.1       22     127.0.0.1        [*] SSH-2.0-OpenSSH_8.2p1 Debian-4
SSH         127.0.0.1       22     127.0.0.1        [+] user:password
```

#### 指定端口

```
#~ nxc http 192.168.1.0/24 --port 2222
```
