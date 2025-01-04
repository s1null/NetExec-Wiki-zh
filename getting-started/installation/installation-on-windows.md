# 🪟 Windows 安装

## 使用 Python 和 pipx

{% hint style="success" %}
如果有 Python 可用,建议使用 pipx 安装 NetExec
{% endhint %}

{% hint style="warning" %}
对于 Windows,安装需要 git 和 Rust。如果你无法安装这两者,请参见下面的独立可执行文件。
{% endhint %}

设置 git、Rust 和 C++:\
[https://git-scm.com/download/win](https://git-scm.com/download/win)\
[https://www.rust-lang.org/tools/install](https://www.rust-lang.org/tools/install)\
[https://visualstudio.microsoft.com/de/visual-cpp-build-tools/](https://visualstudio.microsoft.com/de/visual-cpp-build-tools/)

安装 pipx 并直接从仓库安装 NetExec:

<pre><code><strong>pip install pipx
</strong>python -m pipx ensurepath
python -m pipx install git+https://github.com/Pennyw0rth/NetExec
</code></pre>

重启命令行,你就可以执行 NetExec 了:

```
NetExec
```

## 使用 NetExec 二进制文件

1. 在[发布](https://github.com/Pennyw0rth/NetExec/releases)页面下载最新的 Windows 二进制文件(netexec-windows-latest)
2. 解压文件夹
3. 从命令行运行二进制文件

## 使用 Python ZippApp

{% hint style="warning" %}
并非所有功能都经过测试
{% endhint %}

1. 你也可以使用 Python 的[独立版本](https://www.python.org/downloads/windows/),然后将包含 python.exe 文件的文件夹路径添加到用户的 **PATH** 环境变量中。
2. 在[这里](https://github.com/Pennyw0rth/NetExec/actions/runs/6374124950)下载适用于你特定操作系统和 Python 版本的 ZippApp
3. 然后只需运行二进制文件 `python.exe .\nxc`

{% embed url="https://www.python.org/downloads/windows/" %}

如果你遇到这个错误

`FileNotFoundError: [Errno 2] No such file or directory: 'C:\Users\Admin.shiv\nxc_51b7721208fc3d0af7e301aa9a56e1da0a38e9ec5bc08bfe8cc9ba14853ac5d1.tmp\site-packages\nxc\data\powersploit\CodeExecution\Invoke-ReflectivePEInjection_Resources\DemoDLL_RemoteProcess\DemoDLL_RemoteProcess\DemoDLL_RemoteProcess.vcxproj.filters`

添加以下注册表项:

`REG ADD "HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\FileSystem" /v LongPathsEnabled /t REG_DWORD /d 1 /f`
