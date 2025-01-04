# 🆕 枚举 NFS

目前所有标志都可以匿名工作。

### 枚举 NFS 服务器

检测远程 NFS 服务器和版本。

```
NetExec nfs <ip> 

# Example Output                                                          
NFS         <ip>  <nfs_port>  <ip>   [*] Target supported NFS versions: (3, 4)

```

### 枚举 NFS 共享

使用 `--shares` 标志枚举 NFS 共享。输出显示目标的 `UID、权限、存储使用情况、访问列表`。

```
NetExec nfs <ip> --shares

# Example Output
NFS         <ip>  <nfs_port>  <ip>   [*] Target supported NFS versions: (3, 4)
NFS         <ip>  <nfs_port>  <ip>   [*] Enumerating NFS Shares
NFS         <ip>  <nfs_port>  <ip>   UID        Perms    Storage Usage    Share                          Access List    
NFS         <ip>  <nfs_port>  <ip>   ---        -----    -------------    -----                          -----------    
NFS         <ip>  <nfs_port>  <ip>   2000       rw-      9.2GB/19.5GB    /home/user/Desktop/test        *              
NFS         <ip>  <nfs_port>  <ip>   1000       rw-      9.2GB/19.5GB    /home/user/Desktop/NFSShare    192.168.0.0/24
```

### 枚举 NFS 共享上的文件

使用 `--enum-shares` 递归枚举所有文件和文件夹，默认递归深度为 3 层。可以使用 `--enum-shares 5` 更改深度。输出显示目标的 `UID、权限、文件大小、文件路径、访问列表`。

```
NetExec nfs <ip> --enum-shares

# Example Output
NFS         <ip>  <nfs_port>  <ip>   [*] Target supported NFS versions: (3, 4)
NFS         <ip>  <nfs_port>  <ip>   [*] Enumerating NFS Shares Directories
NFS         <ip>  <nfs_port>  <ip>   [+] /home/user/Desktop/test
NFS         <ip>  <nfs_port>  <ip>   UID        Perms    File Size      File Path                                     Access List    
NFS         <ip>  <nfs_port>  <ip>   ---        -----    ---------      ---------                                     -----------    
NFS         <ip>  <nfs_port>  <ip>   1000       r--      21.0B          /home/user/Desktop/test/test.txt              *              
NFS         <ip>  <nfs_port>  <ip>   0          r--      9.0B           /home/user/Desktop/test/test2.txt             *              
NFS         <ip>  <nfs_port>  <ip>   [+] /home/user/Desktop/NFSShare
NFS         <ip>  <nfs_port>  <ip>   UID        Perms    File Size      File Path                                     Access List    
NFS         <ip>  <nfs_port>  <ip>   ---        -----    ---------      ---------                                     -----------    
NFS         <ip>  <nfs_port>  <ip>   1000       rw-      6.0B           /home/user/Desktop/NFSShare/test.txt          192.168.38.0/24
NFS         <ip>  <nfs_port>  <ip>   1000       rw-      7.0B           /home/user/Desktop/NFSShare/NFS2/test2.txt    192.168.38.0/24,
NFS         <ip>  <nfs_port>  <ip>   1000       rwx      27.0B          /home/user/Desktop/NFSShare/test3.txt         192.168.38.0/24

```