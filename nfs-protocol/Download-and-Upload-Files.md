# 🆕 从 NFS 服务器下载和上传文件

### 下载文件

使用 NetExec 获取远程文件。使用示例：

```
NetExec nfs <ip> --get-file /home/user/Desktop/test/test.txt test.txt

# Example Output                                                          
NFS         <ip>  <nfs_port>  <ip>   [*] Target supported NFS versions: (3, 4)
NFS         <ip>  <nfs_port>  <ip>   [*] Downloading /home/user/Desktop/test/roottest.txt to roottest.txt
NFS         <ip>  <nfs_port>  <ip>   File successfully downloaded to test.txt from /home/user/Desktop/test/test.txt

```

### 上传文件

使用 NetExec 获取远程文件。将远程 NFS 文件以 **777** 权限上传到指定**文件夹**。
使用示例：

```
NetExec nfs <ip> --put-file test2.txt /home/user/Desktop/

# Example Output                                                          
NFS         <ip>  <nfs_port>  <ip>   [*] Target supported NFS versions: (3, 4)
NFS         <ip>  <nfs_port>  <ip>   [*] Uploading from test2.txt to /home/user/Desktop/NFSShare/
NFS         <ip>  <nfs_port>  <ip>   [*] Trying to create /home/user/Desktop/NFSShare/test2.txt
NFS         <ip>  <nfs_port>  <ip>   [+] test2.txt successfully created
NFS         <ip>  <nfs_port>  <ip>   [*] Trying to write data from test2.txt to /home/user/Desktop/NFSShare/
NFS         <ip>  <nfs_port>  <ip>   [+] Data from test2.txt successfully written to /home/user/Desktop/NFSShare/
NFS         <ip>  <nfs_port>  <ip>   File test2.txt successfully uploaded to /home/user/Desktop/NFSShare/

```

**如果本地文件在远程服务器上已存在，NetExec 会询问你是否要覆盖它。**

```
NetExec nfs <ip> --put-file test2.txt /home/user/Desktop/

# Example Output  
NFS         <ip>  <nfs_port>  <ip>   [*] Target supported NFS versions: (3, 4)
NFS         <ip>  <nfs_port>  <ip>   [*] Uploading from test2.txt to /home/user/Desktop/NFSShare/
[!] test2.txt already exists on /home/user/Desktop/NFSShare/. Do you want to overwrite it? [Y/n] Y
NFS         <ip>  <nfs_port>  <ip>   [*] test2.txt already exists on /home/user/Desktop/NFSShare/. Trying to overwrite it...
NFS         <ip>  <nfs_port>  <ip>   [*] Trying to write data from test2.txt to /home/user/Desktop/NFSShare/
NFS         <ip>  <nfs_port>  <ip>   [+] Data from test2.txt successfully written to /home/user/Desktop/NFSShare/
NFS         <ip>  <nfs_port>  <ip>   File test2.txt successfully uploaded to /home/user/Desktop/NFSShare/
```

