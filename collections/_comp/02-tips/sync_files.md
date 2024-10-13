---
title: Sync files across multiple devices using Syncthing
categories: 02-Tips
---

Syncthing 是一个持续的文件同步程序。它可以在**两台或多台计算机之间实时同步文件**，并且能够安全地防止窥探。您的数据只属于您，您有权选择数据存储的位置，是否与第三方共享，以及数据如何通过互联网传输。

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


## 其他同步方式 Resilio Sync

下载：https://www.resilio.com/sync/download/

Install Resilio Agent on TrueNAS Scale: https://connect.resilio.com/hc/en-us/articles/24011844261523-Install-Resilio-Agent-on-TrueNAS-Scale