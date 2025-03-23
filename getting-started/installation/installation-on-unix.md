# 🐧 Unix 安装

## 使用 pipx 安装 NetExec :saxophone:

推荐使用 [pipx](https://github.com/pypa/pipx) 安装 NetExec。这允许你在系统范围内使用 NetExec 和 nxcdb。

{% code overflow="wrap" fullWidth="false" %}
```
sudo apt install pipx git
pipx ensurepath
pipx install git+https://github.com/Pennyw0rth/NetExec
```
{% endcode %}

打开一个新的 shell 就可以开始使用了:

```
NetExec
nxcdb
```

通过 pipx 更新:

```
pipx upgrade netexec        # 如果有新版本将会更新
pipx reinstall netexec      # 强制从 github 下载最新提交
```

## Kali 安装 :dragon_face:

```
apt update
apt install netexec
```

## BlackArch 安装 :dagger:

```
pacman -Syu netexec
```

## ParrotSec 安装 🦜

```
apt update
apt install netexec
```

## 在其他 Unix 发行版上的可用性 :penguin:

[![打包状态](https://repology.org/badge/vertical-allrepos/netexec.svg)](https://repology.org/project/netexec/versions)

## 使用 Poetry 进行开发安装 :postal_horn:

你需要安装 [Poetry](https://python-poetry.org/docs/#installation),这是 nxc 用来管理依赖项的工具。你应该使用 [pipx](https://github.com/pypa/pipx) 来安装 poetry,因为我们的动态版本插件可能会崩溃。

```
apt install pipx git
pipx ensurepath
pipx install poetry
poetry self add "poetry-dynamic-versioning[plugin]"
poetry dynamic-versioning enable
```

现在 poetry 已经设置好了,我们可以下载 NetExec 仓库并安装其依赖项:

```
git clone https://github.com/Pennyw0rth/NetExec
cd NetExec
poetry install
poetry run NetExec
```


## 二进制文件

我们建议通过 pipx/pip 安装,但如果你想使用预编译的二进制文件,请转到[发布页面](https://github.com/Pennyw0rth/NetExec/releases)并下载适当的二进制文件。
