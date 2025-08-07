---
title: 跨平台同步数据
categories: 02-Tips
---


## 软件对比

Syncthing 是一个持续的文件同步程序。它可以在**两台或多台计算机之间实时同步文件**，并且能够安全地防止窥探。您的数据只属于您，您有权选择数据存储的位置，是否与第三方共享，以及数据如何通过互联网传输。

| 比较维度            | Syncthing                              | Resilio Sync                         |
|---------------------|----------------------------------------|--------------------------------------|
| **开源性**          | 开源软件，免费使用，GPLv3许可证        | 封闭源代码，提供免费和付费版本      |
| **平台支持**        | 支持Windows、macOS、Linux、BSD、Android、iOS等 | 支持Windows、macOS、Linux、FreeBSD、Android、iOS等 |
| **易用性**          | 界面简洁直观，适合技术用户              | 界面友好，适合普通用户，易上手       |
| **隐私与安全**      | 端到端加密，无需中介服务器，用户数据完全掌控 | 使用AES-128加密，有依赖第三方服务器的风险（用于付费版的中继） |
| **同步速度**        | 基于用户之间的直连网络传输，可能因网络状况有所影响 | 使用P2P协议，速度更快，尤其是付费版本中的高速同步 |
| **文件大小限制**    | 无文件大小限制                         | 免费版有文件大小限制，Pro版本无限制  |
| **版本控制**        | 支持文件版本历史，但功能相对简单        | 支持版本历史与高级版本控制功能       |
| **配置难度**        | 需要手动配置与管理设备间连接            | 自动发现设备连接，配置较为简单       |
| **群组同步**        | 支持，设置较复杂                       | 支持群组同步，设置较为简单           |
| **带宽控制**        | 支持限速功能                           | 提供详细的限速功能                  |
| **扩展功能**        | 专注文件同步，无附加功能               | 付费版提供更多高级功能（如选择性同步等） |
| **成本**            | 完全免费                              | 免费版有限制，付费版（Pro）提供更多功能 |
| **社区支持**        | 活跃的开源社区，提供持续支持            | 由公司支持，付费用户可获得技术支持   |

## Installation

### Windows

自 [Syncthing 官网](https://syncthing.net/)下载合适的安装包：https://syncthing.net/downloads/。

软件为绿色免安装版，解压即可运行 Syncthing.exe 通过 Web 浏览器打开管理页面。


### Android

1. 下载 F-Droid ，需魔法：https://f-droid.org/
2. 将下载好的 F-Droid.apk 文件传输到安卓设备上，安装，并对其使用魔法。
3. 打开 F-Droid ，搜索并安装 Syncthing。

### Linux

打开 Terminal，安装：
```bash
# For Ubuntu
sudo apt install syncthing

# For Arch
sudo pacman -S syncthing

# flatpak
flatpak install syncthing
```
运行 syncthing 打开 Web 管理界面。

### Docker

```
yum install -y yum-utils
yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
yum install docker-ce -y

# 启动 Docker
systemctl enable docker --now
# 安装 docker-compose
curl -L https://github.com/docker/compose/releases/download/v2.12.2/docker-compose-linux-x86_64 -o /usr/local/bin/docker-compose
chmod a+x /usr/local/bin/docker-compose

# 创建项目目录
mkdir -p /data/syncthing

# 创建docker-compose文件，内容如下：
cd /data/synthing
cat > docker-compose.yaml <<EOF
version: "3"
services:
  syncthing:
    image: syncthing/syncthing:1.25
    container_name: syncthing
    hostname: my-syncthing
    environment:
      - PUID=1000
      - PGID=1000
    volumes:
      - /data/syncthing/data/myfiles:/var/syncthing/myfiles
    network_mode: host
    restart: unless-stopped

# 创建docker容器
cd /data/synthing
docker-compose up -d

```

### iOS/ipadOS

在 AppStore 中安装 Möbius Sync。

### Mac OS

自 [Syncthing 官网](https://syncthing.net/)下载合适的安装包：https://syncthing.net/downloads/。

### TrueNAS Scale

1. 打开 TrueNAS 的管理页面，点击 APP - Discover Apps。
2. 搜索 Syncthing，并点击对应图表。点击 Install。
3. 设置 User ID、Group ID 为你想要以其权限访问文件的用户。
4. 设置 Web Port 为你想以其访问 Web 管理页面的端口号码。
5. 设置 Syncthing Config Storage 的 Type 为 Host Path，并将 Host Path 选项设置为你想要存放配置文件的地点。
6. 点击 Additional Storage 右侧的 ADD 增加 Syncthing 可以访问的 NAS 服务器地址。
7. 点击 Install，并等待安装完毕。

## 快速使用

### 添加设备

1. 在设备A的界面上，点击右上角⚙标志，点“显示ID”。

2. 在另外一台设备B上，通过 ID 或者二维码添加设备。

3. 返回设备 A，通过 B 的添加请求，并为其命名。

### 添加文件夹

1. 添加文件夹
2. 填入“标签”、和“路径”。
3. 点击“共享”，选择要共想给的设备。
4. 可以在后面设置版本控制策略（类似于回收站）和全文件检查时间。

## 内网穿透

参见：https://blog.csdn.net/m0_74760716/article/details/132211914


## 设置静默开机自启动

官方文档：https://docs.syncthing.net/users/autostart.html


### Windows
在 syncthing 程序根目录下创建start_syncthing_hidden.ps1，内容如下：
```powershell
$current_file_path = (Get-Location).path
$exe_path = $current_file_path + "\syncthing.exe"
Start-Process -FilePath $exe_path -WindowStyle Hidden
```
在 syncthing 程序根目录下创建 start_sycthing.bat，，内容如下：
```bat
@echo off
set bat_path=%~dp0
PowerShell.exe -NoProfile -Command "& '$bat_path$\start_syncthing_hidden.ps1'"
```

WIN+R 运行：taskschd.msc，即计划任务。

创建任务，名称为 syncthing，选中“RUn whether user is logged on or not”。

如果要想在登陆用户时运行：点击“触发器（triggers）”——“新建”——在 Begin the task 选项选择“at log on”——在Settings 选项选择 Specific User。

如果要想在系统启动时运行：点击“触发器（triggers）”——“新建”——在 Begin the task 选项选择“at startup”

### Linux

1. **创建用户**：创建一个将运行服务的用户，或者选择一个现有用户。通常情况下，这将是您的个人用户账户。

2. **复制服务文件**：（如果您的发行版的安装包已经包含了这些文件，您可以跳过此步骤。）从Git仓库中复制 `syncthing.service` 文件到用户实例的加载路径。为了避免使用 `root` 权限，您可以将该文件复制到主目录下的以下文件夹：`~/.config/systemd/user/`。

3. **启用并启动服务**：使用以下命令启用并启动Syncthing用户服务：

```bash
systemctl --user enable syncthing.service
systemctl --user start syncthing.service
```

5. **加密的主目录注意事项（适用于Debian/Ubuntu）**：如果您的主目录使用 `eCryptfs` 加密（在Debian/Ubuntu上），您需要进行[Ubuntu bug 1734290](https://bugs.launchpad.net/ubuntu/+source/systemd/+bug/1734290)中描述的更改。否则，用户服务将无法启动，因为系统默认会在主目录解密之前检查用户服务。

6. **系统启动时自动启动**：如果无法使用系统服务，可以通过systemd的“**持久化**（lingering）”功能在开机时自动启动systemd用户实例（在登录之前）。使用 `loginctl enable-linger` 命令为特定用户启用此功能。

```bash
loginctl enable-linger your-username
```

这样设置后，Syncthing服务将在您的系统启动时自动运行，即使您尚未登录。

## 其他同步方式 Resilio Sync

下载：https://www.resilio.com/sync/download/

Install Resilio Agent on TrueNAS Scale: https://connect.resilio.com/hc/en-us/articles/24011844261523-Install-Resilio-Agent-on-TrueNAS-Scale