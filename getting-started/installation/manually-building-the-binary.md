---
description: >-
  如果你想自己构建独立二进制文件,这里有一个教程供你参考
---

# 🛠️ 手动构建二进制文件

{% hint style="warning" %}
由于依赖项会随时间变化,此过程可能会出现错误。如果你不需要出于特定原因自己编译二进制文件,建议使用来自 [GitHub](https://github.com/Pennyw0rth/NetExec/releases) 的预编译二进制文件。
{% endhint %}

## Linux

克隆仓库:

```
git clone https://github.com/Pennyw0rth/NetExec.git
cd NetExec
```

为 pip 创建虚拟环境,安装 pyinstaller 并构建二进制文件:

```
virtualenv env
source env/bin/activate
sudo apt remove python3-pyinstaller    # 删除旧的 apt pyinstaller
pip install pyinstaller .
pyinstaller netexec.spec    # 这将编译二进制文件
```

现在你应该有编译好的二进制文件:

```
./dist/nxc
```

## Windows

{% hint style="warning" %}
Windows 需要 Rust 来构建 python 依赖项。
{% endhint %}

转到 Rust 安装页面并按照安装说明操作:\
[https://www.rust-lang.org/tools/install](https://www.rust-lang.org/tools/install)

安装 Rust 后克隆仓库:

```
git clone https://github.com/Pennyw0rth/NetExec.git
cd NetExec
```

设置虚拟环境,安装所需包并构建二进制文件:

```
python -m venv env
source env/Scripts/activate
pip install pyinstaller pillow .
pyinstaller netexec.spec
```

现在你应该有编译好的二进制文件:

```
./dist/nxc.exe
```
