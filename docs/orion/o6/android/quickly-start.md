---
sidebar_position: 1
---

# 快速上手

主要介绍如何刷 Android BIOS 和安装 Android 系统。

## 使用前提

- 主板：瑞莎 Orion O6
- U 盘：用于更新 BIOS
- 系统启动盘：NVMe SSD
- 数据线：USB Type-C 数据线
- 显示器：用于显示 BIOS 设置界面
- 电源适配器：USB-C 20V 电源适配器（兼容 PD 协议）
- PC 主机: Windows / Linux / MacOS, 安装 fastboot 工具
- 可选设备：串口数据线

说明：其中可选设备用于刷 BIOS，刷 BIOS 可以通过串口或者显示器操作。

:::tip 推荐配件

- [瑞莎 PD 65W 电源适配器](https://radxa.com/products/accessories/power-pd-65w)

:::

## 刷写安卓 BIOS

在开始之前，请确保您已完成所有准备工作。

### 准备工作

#### 1. 安装必要工具

我们需要在主机上安装 adb 和 fastboot 工具。

:::tip 系统环境
推荐使用 Ubuntu 系统进行系统安装。
:::

<NewCodeBlock tip="Ubuntu-PC$" type="device">

```
sudo apt update
sudo apt install android-tools-adb android-tools-fastboot
```

</NewCodeBlock>

#### 2. 制作 BIOS U 盘

访问 [资源汇总下载](../download.md#android) 页面，下载最新的安卓 BIOS 文件，并将其解压到 U 盘的根目录。

### 硬件连接

:::tip 接口说明
Orion O6 主板配备两个 USB Type-C 接口：

- **数据接口**：靠近 USB-A 接口，用于连接 PC 进行数据传输。
- **电源接口**：靠近电源按键，用于连接电源适配器。
  :::

- ① 将 NVMe SSD 安装到主板上。

- ② 将制作好的 BIOS U 盘插入主板的 USB-A 接口。

- ③ 使用 USB Type-C 数据线将主板的 **数据接口** 连接到 PC。

- ④ (可选) 如需通过串口查看日志，请连接串口调试线至主板的 UART2 接口。

- ⑤ 连接显示器到主板的 HDMI 或 DP 接口。

- ⑥ 使用 USB-C 电源适配器为主板的 **电源接口** 供电。

<div style={{textAlign: 'center'}}>
    <img src="/img/o6/android/android-install-system.webp" style={{width: '100%', maxWidth: '1200px'}} />
</div>


### 操作步骤

#### 1. 进入 BIOS 设置界面

主板通电后，当看到 Radxa Logo 或串口输出 `Press ESCAPE for boot options` 时，立即短按键盘上的 `Esc` 键，即可进入 BIOS 设置界面。

- **通过显示器**

<div style={{textAlign: 'center'}}>
    <img src="/img/o6/android/burn-bios-go.webp" style={{width: '50%', maxWidth: '1200px'}} />
</div>

- **通过串口**

```
Tianocore/EDK2 firmware version 0.3.0-1
Press ESCAPE for boot options
```

#### 2. 运行 BIOS 刷写脚本

进入 BIOS 后，选择 `Boot Manager` -> `EFI Shell`。系统将自动检测并运行 U 盘中的 `startup.nsh` 脚本来完成 BIOS 刷写。

<div style={{textAlign: 'center'}}>
    <img src="/img/o6/android/burn-bios-manager.webp" style={{width: '100%', maxWidth: '600px'}} />
</div>

_进入 Boot Manager_

<div style={{textAlign: 'center'}}>
    <img src="/img/o6/android/burn-bios-efi.webp" style={{width: '100%', maxWidth: '600px'}} />
</div>

_选择 EFI Shell_

<div style={{textAlign: 'center'}}>
    <img src="/img/o6/android/burn-bios-sh.webp" style={{width: '100%', maxWidth: '600px'}} />
</div>

_自动运行刷写脚本_

#### 3. 确认进入 Fastboot 模式

BIOS 刷写完成后，主板会自动重启并进入 Fastboot 模式。

<div style={{textAlign: 'center'}}>
    <img src="/img/o6/android/burn-bios-fastboot.webp" style={{width: '100%', maxWidth: '600px'}} />
</div>

## 安装 Android 系统

BIOS 刷写完成后，主板已进入 Fastboot 模式，接下来我们可以开始安装 Android 系统。

### 1. 下载并解压系统镜像

访问 [资源汇总下载](../download.md#android) 页面，下载最新的 Android 系统镜像，并将其解压到您的 PC 本地。

### 2. 刷入系统镜像

在 PC 上打开终端，进入解压后的 Android 系统镜像目录，然后运行 `android_flush_images.sh` 脚本。

<NewCodeBlock tip="Ubuntu-PC$" type="device">

```
./android_flush_images.sh
```

</NewCodeBlock>

脚本将自动完成系统刷写。刷写成功后，主板会自动重启并进入 Android 系统。
