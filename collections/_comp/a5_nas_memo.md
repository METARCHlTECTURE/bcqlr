---
title: DIY Low Power Consumption NAS 
highlight: true
---

## Hardware Information

### High-capacity Local Area Network NAS with 10G trans

**Main Devices**: 
  - CPU: Intel Xeon E5-1235L v5 4C4T 3GHz 25wTDP LGA1151
  - MB: MSI C236a Workstation 305mm X 244mm
  - Memory: Sk Hynix DDR4 2133MHz ECC 16GB * 4
  - Gpu: Intel Graphics Hd P530 192sp Integrated

**Stroage Devices**: 
  - Boot-Pool, Mirror:
    - Samsung PM961 128GB * 2
  - Appdata-Pool, Raid Z1:
    - Samsung PM961 512GB
    - Samsung 970 Evo Plus 512GB
    - Samsung 980 512GB 
  - Data-Pool, Raid Z2:
    - HHD: Seagate Exos st1800nm000j 18TB * 6
  - Adaptor:
    - JEYI SK18 M.2 NVME To PCIE4.0x4 * 2
    - JEYI SK1 M.2 NVME To PCIE4.0x1 * 2

**Suplementary Devices**: 
  - Chassis: Antec P101S ATX Chassis
  - PSU: MSI MPG A650GF 650w Gold Fully Modular
  - Cooler: Phantom Spirit 120 SE 265wTDP
  - Netword Adaptor: 
    - HP 10G RJ45x2
    - RTL8125 2.5G
  - UPS: APC Schneider BK650M2-CH 650VA
  - CPU Thermal Gease: Honeywell PTM7950 Phase-change-pad
  - SSD Thermal Gease: Techinno Lv800

### ITX NAS

**Main Devices**: 
  - CPU: Intel Core i5 11500H 6C12T 4.6GHz 45wTDP FCBGA1787
  - Motherboard: Erying Skyline Hm570 ITX 170mm X 170mm
  - Memory: Kingbank DDR4 2133MHz 8GB + 16GB
  - GPU: Intel UHD Graphics XE 750 32eu

**Storage Devices**: 
  - Boot-Pool SSD, Mirror:
    - SSD: Samsung PM961 128GB * 2
  - Appdata-Pool, Stripe:
    - SSD: KIOXIA RC20 1TB
    - Adpator: JEYI MX16 M.2 Nvme To PCIE3.0x4
  - Media Data-Pool, Stripe:
    - HHD: Seagate Barracuda 5TB
    - HHD: Seagate Barracuda 4TB
  
**Supplementary Devices**: 
  - Chassis: Sirius S40 8.5L ITX
  - PSU: Thermaltake Toughpower SFX 450w Gold Fully Modular
  - Cooler: Thermalright axp90-53 Black
  - CPU Thermal Gease: Honeywell PTM7950 Phase-change-pad + Geekcooling 5
  - SSD Thermal Gease: Techinno LV800



## Truenas Scale Quick Start Guide

### Make TrueNAS USB Flash Disk

Prerequisite:
  1. USB Flash Disk with 4 GiB Storage at least
  2. A computer with network connection

1. Download TrueNAS Scale ISO image in official website: https://manjaro.com/.
2. Download Rufus 4.1p: https://rufus.ie/.
3. Make TrueNAS USB Flash Disk by rufus with default configuration and wait until the progress is completed.
4. Insert USB Flash Disk.
5. Press F1/F2/F8/F10/Shift+F10/Shift+Fn+F10/DEL, enter BIOS and make sure the boot priority of USB Flash Disk is highest.
6. Install TrueNAS Scale.
  - You can choose multiple hard disk to install to enable raid mode to gain more stability.
  - TrueNAS Scale encourage users maintain NAS with "admin" account, rather than "root" with TrueNAS Core.
7. Set Password.
8. Reboot, keep the ip address shown in the monitor and access the management site in web browser with another computer.

### 2. (Optional) Change Time Zone and Locale.

In the management site:
1. SYSTEM.
2. GENERAL.
3. LOCALIZATION SETTINGS.
4. SETTINGS.
5. Asia/Shanghai.
6. SAVE.

### 3. Disable DHCP service and allocate a static ip address to NAS.

1. NETWORK.
2. INTERFACES.
3. Click the network card.
4. Deselect DHCP checkbox.
5. Add ALIASES, input the ip address which you prefer to access NAS management site with (generally start with 193.168.1).
6. Input NETWORK MASK, which generally is 24 (it means your local network ip address range from xxx.xxx.xxx.1 to xxx.xxx.xxx.255).
6.  的 IP Addresses 中，输入欲访问的地址、掩码（一般为24） - APPLY`

此时出现手动设置网关，在对话框中输入。

此时出现测试设置对话框。

`勾选 Confirm，点击 Test Changes - Apply Changes。`

此时重新登陆更改后的 IP 地址，会出现确认更改内容的对话框，点击`确认`。之后提示设置已更改。

### 4.设置主机名称、 DNS 服务器

`Network - Interfaces - Global Configuration - SETTINGS - 输入 hostname - 输入 DNS 地址`

### 5.创建 pool 和 dataset

创建 pool: 

`Storage - Create Pool - 在 Pool Manager 中，键入名称 - 选中所有硬盘，添加进 Data VDev 中 - 在 Data VDev 中选择阵列模式 - Create - 弹出警告窗口，选中 Confirm，并点击 Create Pool`

> 阵列模式中: Stripe 为 Raid 0，Mirror 为 Raid 1，此外还有 Z1、Z2、Z3。

Pool 的根目录位于: /mnt/[POOL_NAME]

创建 dataset: 

`Dataset - ADD DATASET - 键入 Dataset 名称 - SAVE`

### 6.添加用户

`Credentials - Local User - ADD - 键入Full Name、Username、Password - （optional）设置 Home Directory - SAVE`

### 7.更改 Dataset 的访问权限

`Datasets - Permissions - EDIT - 给 Other 组勾选写入权限`

### 8.使用 Samba 共享

`Shares - 点击 Windows(SMB) Shares 的“⋮”标志，点击 Turn On Service - ADD - 选中需要共享的数据集 - SAVE - 弹出的对话框中选择 Restart Service`

## 客户机访问 NAS 存储服务

### Windows

`Win+x 开启运行 - 输入 \\ + NAS 服务器的内网地址 - 运行`

在打开的文件夹中，右键点击 Dataset 的文件夹，点击“映射为网络驱动器“，即可在计算机根文件夹中看到此驱动器。

### Linux

1. 安装 smbclient

```bash

# arch/manjaro
sudo pacman -S smbclient
# debian/ubuntu
sudo apt install smblient
# RHEL
sudo yum install samba-client
```

2. 访问 Samba 共享资源

```bash
smbclient //[HOSTHAME_OR_IP]/[SHARE_NAME] -U [USERNAME]
```
3. 根据提示输入密码，成功连接后，显示 smb: \> 命令行。

4. 将 datasets 挂载到本地: 安装 cifs-utils，并创建挂载点

```bash
sudo mkdir /mnt/[MOUNT_DIR_NAME]
```
5. 将远程目录挂载在刚建好的本地目录上

```bash
sudo mount -t cifs //[HOSTHAME_OR_IP]/[SHARE_NAME] /mnt/[MOUNT_DIR_NAME] -o username=[USERNAME],password=[PASSWORD],iocharset=utf8,dir_mode=0777,file_mode=0777
```
> 使用 df-h 查看挂载情况；使用 ll /mnt/[MOUNT_DIR_NAME] 查看文件

6. 取消挂载

```bash
umount /mnt/smbmount
```

7. 设置开机自动挂载

在 /etc/fstab 文件中加入以下内容: 

```bash
//[HOSTNAME_OR_IP]/[SHARE_NAME] /mnt/[MOUNT_DIR_NAME]  cifs  username=[USERNAME],password=[PASSWORD],soft,rw  0 0
```

## Storage Dashboard 介绍

该页面列存储池的详细信息: 
- Export/Disconnet: 暂时下线、上线某存储池。
- Topology - Manage Devices: 物理磁盘的状态，出错数量，或增加VDEV。
- Usage - Manage Datasets: 管理数据集。
- ZFS Health - Scrub: 手动校验硬盘。默认设定下，每周日 0 点进行一次校验，持续约 12 小时，并不需要手动校验。
- Disk Health - Manage Disks: 管理物理磁盘。

## 进阶使用

### 为已有存储池添加新的物理磁盘

Storage - 在 Unassigned Disks 标签中，点击 Add to Pool - 选择 Existing Pool - 选择要添加的存储池的名称。

注意: 
1. 此时存储池拥有多个 VDevs。这样的多个 VDevs 要保持物理磁盘的数量一致。并且此时多个 VDevs 只能使用相同的 Raid 模式。当然，存储池建立后不建议扩容，如有需要则新建存储池（会造成文件访问地址改变）。
2. VDevs 一旦添加入存储池，则无法再分离出来，这是因为文件是离散存在于每个 VDevs 中的。

### 为已有存储池更换硬盘

Storage - 在 Topology 标签中点击 Manage Devices - 点击需要替换的硬盘 - 在弹出的对话框中选择替换为的硬盘 - 如果硬盘已分区，需要勾选 Force - Replace Disk。

注意: 
1. 用于替换的硬盘必须容量大于已有的硬盘，无论其被占用了多少容量。
2. 替换需要一定时间，受其中的数据多少影响。

### 迁移存储池

> 硬盘中记录了其曾经存在的存储池信息，所有物理硬盘存在则可以重建。

将已有的存储池断开连接: 

Storage - Export/Disconnet


导入存储池: 

Storage - Import Pool - 在右侧边栏选择导入的存储池名称。

### 硬盘损坏数据未丢失，恢复安全等级

将新硬盘加入物理主机后，Storage - 在 Topology 标签中点击 Manage Devices - 点击 REMOVED 硬盘 - 在 Disk Info 中点击 Replace - 在弹出的对话框中选择新硬盘 - 等待系统 Resilvering 结束

> 在 Resilvering 过程中，最好不要对 NAS 主机进行其他操作

### 测试硬盘顺序读取速度

System - Shell: 

```bash
cd /mnt/[POOL_NAME]/[DATASET_NAME]
fio --name=test --size=50g --rw=write --ioengine=posixaio --direct=1 --bs=1m
```

### 对存储池进行加密

## 基础知识

### 主要 NAS 操作系统比较

TureNAS Core
- 由 FreeNAS 演化而来，基于 FreeBSD；
- 开源系统，支持网卡型号多，适合高速存储
- ZFS，支持数据实时压缩；利用内存为缓存，保持硬盘寿命；实时快照功能

TrueNas Scale
- 基于 Debian，增加了 Docker 和虚拟机的支持

群晖
- 支持网卡型号少、万兆升级贵
- 有应用商店，不需要手动换安装源
- 拥有文件回收站、快照、版本控制功能。
- 手机 app 支持好，如 Moments 管理照片；Drive 管理文档；Plex 管理视频

UNRAID
- 拥有校验盘机制
- 对于不同容量的硬盘支持较好
- 无法组建 Raid

openmediavault
- 相当于去掉套件中心、app服务的免费版群晖
- 使用 protainer 管理 Docker
- 可安装 ZFS，支持快照


### Raid 模式比较

Raid 0: 两盘并联，不损失容量，无冗余，速度快；任意一盘损坏则数据丢失。安全性低。

Raid 1: N 盘互为镜像，损失 N-1 盘容量，读取速度翻 N 倍，写入速度不变；至多可损坏 N-1 块硬盘（N至少为2）。性价比低。

Raid 2: 至少 3 盘、分段写入、实时编码、汉明码校验。读写时校验数据，硬件开销大。

Raid 3: 由 Raid 2 衍生，至少 3 盘、专门设立校校验。每次读写都访问校验盘，因而易损坏。校验盘损坏则数据丢失。以 Bit 分割数据。

Raid 4: 由 Raid 3 衍生，以数据块分割数据。小文件读取快，但非校验盘损坏时，数据恢复概率较 Raid 3 低。

Raid 5: 类似 Raid 3，分散存储校验数据，至少 3 盘，损失 1 盘空间。至多可损坏 1 盘。有极低概率造成 URE（不可恢复性读取错误），在重建阵列时出现则需要重新开始。重建难度大，安全性较 Raid 6 低。

Raid F1: 由 Raid 5 衍生，适用于固态硬盘。

Raid 6: 类似 Raid 5，至少 4 盘，两盘校验。至多可损坏 2 盘。写入慢于 Raid 5。

Raid 7: 专利属于 SCC 公司，需付费。

Raid 10: 至少 4 盘，硬盘两两先组成 Raid 1，再组成 Raid 0。损失 50% 容量。安全性高。

JBOD: 将所有硬盘组成一个逻辑分区，读取速度不变，不损失容量。第一块盘记录数据分段表，损坏则阵列损坏；其他盘损害只影响自身数据。安全性低。

Unraid: 使用 1-2 盘作为数据校验盘。至多可损坏 1-2 盘，非校验盘损坏只影响自身数据。便于扩容。写入最慢，收费。

SHR: 群晖特有，自动判断 Raid 模式，适合新手。可设置 1-2 冗余盘。

Raid Z: ZFS 文件系统特性，不需要额外软硬件。需要大量内存，最好为 ECC 内存。扩容难。
  - Raid Z1: 类似 Raid 5，2 盘数据、1 盘校验。
  - Raid Z2: 类似 Raid 6，2 盘数据、2 盘校验。
  - Raid Z3: 2 盘数据、3 盘校验。

### 应用场景

- 手机相机的图片视频备份
- 家庭影院的片源存档
- Windows/MacOS 系统备份
- 手机、电脑 NAS 多客户端
- 高速、安全存储
- 多用户权限控制
- 文件删除恢复、快照、版本控制
- 文件远程存储、取用

## NAS 的坑

CPU
- 是否带有核显，以提供硬件视频解码能力。带有核显的低功耗志强E3处理器很少，如 1235L v5，但 1240L v5 则无核显。
- NAS系统对核显驱动更新慢，酷睿 10 代以上自带的核显不支持
- NAS 系统对 CPU 性能要求极低，需要更强性能的需求有: 
  - 使用Docker
  - 万兆慢速传输
  - 多用户视频在线剪辑
  - 使用 ZFS 文件系统
  - 使用虚拟机

内存
- TrueNAS 等使用 ZFS 文件系统的操作系统，需要内存带有 ECC 功能，以应对太阳黑子、电磁干扰带来的比特翻转
- CPU 是否支持 Ecc、REG ECC 内存
- 内存类型是 纯 ECC，还是 REG ECC。一般志强 E3、部分奔腾支持纯 ECC，志强 E5等高端服务器CPU支持REG ECC
- REG ECC 的功耗、发热大，单条 10W，需要强力机箱风扇
- 内存频率、速度不重要，容量 8G 起步。若使用 TrueNAS，则需要大容量内存做缓存。一般来说，10TB 容量对应 16-32GB 内存，40 TB 容量对应 32-64GB 内存，超过 100TB 容量对应 64-128GB 内存。

主板
- 硬盘 Sata 接口是否与 M.2 的口冲突？部分主板使用 M.2 接口后会屏蔽部分 Sata 接口
- 淘宝的 NAS ITX 妖板很坑，其自带的散热器噪音大、网卡弱、硬盘接口冲突
- 安装系统时，需要暂时使用视频输出。此时需要了解该主板是否带有视频接口；若无，可以暂时插入一个显卡使用，安装完毕拔出即可。工作站主板、工控主板，如 X150 系列，无视频接口。
- 不要使用自带 Raid 阵列功能的主板！超频失败、主板电池没电均会造成阵列信息丢失
- 尔英（ERYING）的板载 CPU 主板虽然在规格上非常适合做低功耗高性能的 NAS，但是该主板在加入“存有数据的机械硬盘时”可能会无法开机。此外，主板离电后也可能无法开机。

硬盘
- 异常便宜的都是矿盘
- 如果对速度不敏感，5400 转硬盘即够用
- 2.5 寸硬盘大多是 SMR 硬盘，3.5 寸也有，最好用 CMR 硬盘
- 希捷 Exos 企业盘读写的噪音 在43-48 分贝之间，远高于环境噪音 30-36 分贝，西数则超过 50 分贝。对噪音敏感则应选择低转速 NAS 专用盘
- 群晖等专用机箱无法使用企业盘，因为闷罐小机箱散热差，本身只为 NAS 专用盘设计
- 部分小作坊的机箱硬盘减震措施很差，不适合使用企业盘
- 若使用 2U、4U 的刀片服务器机箱，可能因为其硬盘堆叠密度过高，普通 3000 转风扇无法散热不佳，需要上万转工业风扇
- NAS 系统的安装盘仅需要超过 16GB 大小。可组 RAID1 保证系统稳定性。即使 NAS 系统损坏，也可通过重装系统恢复磁盘阵列。

电源
- 注意很多 NAS 机箱只支持 1U 电源，转换率低下噪音大
- 注意功耗计算，若不支持硬盘顺序启动，企业硬盘启动时需要 25-36w 的功耗，每个 REG ECC 内存 10 w 功耗
- 注意电源给 SATA 设备的功耗，是否小于总功耗。海韵 GX650 可以将 650W 功耗自由分配给硬盘，但微星 MPG A650GF 只能给 SATA 设备 300w 功耗
- 注意电源最多可以分出几个 SATA 接口。模组线一般是一拖三、一拖四，但切忌一条供电线连接超过 4 块硬盘
- 若工作环境可能断电，搭配 UPS 电源使用。UPS 可通过数据线给 NAS 发送关机指令。

网卡
- 一些老旧型号的 10G 网卡，不支持向下兼容 2.5G 协议，如 Intel x540。Intel x550 显卡则支持 10G 2.5G 1G 协议
- 网卡是否需要驱动？使用的 NAS 系统是否有该驱动？一般来说，封闭的群晖对网卡的支持数量少
- 一些服务器 PCIE 的网卡，其接口与普通主板的 PCIE 插槽不兼容，需要转接卡
- 可使用无驱动网卡

机箱
- 若使用 nas 专用机箱，注意CPU 散热器限高，大部分机箱不支持塔式。下压式散热一般支持比较好，散热能力足够
- 很多专用机箱只支持 1u、sfx 电源
- 注意机箱与硬盘的连接方式，是通过 sata 数据线，还是支持热插拔的背板

操作系统
- 家用最好用群晖、OMV，对手机平台支持好
- 黑群晖一般需要外置存储设备引导启动，一般为 U 盘或者内置的硬盘。注意该设备是否耐用、稳定、耐热。
- 视频在线剪辑等专业用途使用 TureNAS，必须搭配 ECC 内存
- 不推荐小公司的成品 NAS。其使用自有的操作系统，若公司倒闭则对系统停止支持

使用中
- Raid 5 在一盘损坏后，重建阵列十分困难。这时因为，在读取数据时，有极低概率造成 URE（不可恢复性读取错误），平均读取约每 12 TB数据产生一次错误。产生 URE 后，重建阵列停止，需重新开始
- Raid Z、Z2、Z3 不适合扩容。UNRAID 扩容比较方便。
