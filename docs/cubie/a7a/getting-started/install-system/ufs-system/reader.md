---
sidebar_position: 2
---

# 使用瑞莎 eMMC/UFS 二合一模块读卡器

主要介绍 UFS 模块搭配瑞莎 eMMC/UFS 二合一模块读卡器使用并安装系统到 UFS 模块中。

:::warning
安装系统会格式化 UFS 模块，如果有重要数据请提前备份！
:::

## 硬件准备

您需要提前准备以下硬件：

- 系统启动介质：UFS 模块
- 读卡器：eMMC/UFS 二合一模块读卡器

:::tip 推荐配件

- [瑞莎 UFS 模块](https://radxa.com/products/accessories/ufs-module)
- [瑞莎 eMMC/UFS 二合一模块读卡器](https://radxa.com/products/accessories/emmc-ufs-module-reader)
  :::

## 硬件连接

将 UFS 模块安装到读卡器中，然后将读卡器插入 PC 的 USB 端口上。

:::caution

UFS 模块安装步骤：

1. 确保 UFS 模块的缺角和读卡器的接口方向一致
2. 确保 UFS 模块底部卡槽接口和瑞莎 eMMC / UFS 二合一模块读卡器的接口对齐
3. 轻微用力按压 UFS 模块一端的接口，听到"滴"的声音说明安装成功，同样的方法按压另一端的接口，确保 UFS 模块安装成功。
   :::

<div style={{textAlign: 'center'}}>
  <img src="/img/cubie/a7a/a7a-ufs-reader.webp" style={{width: '100%', maxWidth: '1200px'}} />
</div>

## 软件准备

使用开源镜像烧录工具 Etcher 烧写系统镜像文件到 UFS 模块。

### 下载系统镜像

进入 [资源汇总下载](../../../download) 页面下载并解压系统镜像文件到 PC 上。

### 下载 Etcher

进入 Balena Etcher 官网下载系统对应平台的软件：[balenaEtcher](https://etcher.balena.io)。

<div style={{textAlign: 'center'}}>
<img src="/img/rock4/4d/down-etcher-01.webp" style={{width: '100%', maxWidth: '1200px'}} />
</div>

根据自己的系统平台和架构下载对应的软件安装包。

<div style={{textAlign: 'center'}}>
<img src="/img/rock4/4d/down-etcher-02.webp" style={{width: '100%', maxWidth: '1200px'}} />
</div>

### 使用 Etcher

下载完成后，双击打开 Etcher 应用。

:::tip

- Windows

下载的文件是 `*.exe` 格式的安装包，双击程序就可以运行。

- Linux

推荐下载 `*.zip` 格式的压缩包，解压后双击程序就可以运行。

- MacOS

根据自己的系统架构下载对应的 `*.dmg` 文件,双击打开后，将软件拖拽到 Applications 文件夹进行安装，安装完成后双击应用图标运行。

:::

<div style={{textAlign: 'center'}}>
  <img src="/img/rock4/4d/down-etcher-00.webp" style={{width: '100%', maxWidth: '1200px'}} />
</div>

- 安装系统镜像

1. 选择主板对应的系统镜像：点击 `Flash from file` 选项，选择自己提前下载并解压好的系统镜像文件。

<div style={{textAlign: 'center'}}>
  <img src="/img/rock4/4d/etcher-01.webp" style={{width: '100%', maxWidth: '1200px'}} />
</div>

2. 选择 UFS 模块对应的磁盘：点击 `Select target` 选项，选择自己接入 PC 的读卡器对应磁盘设备。

:::danger
请勿选错磁盘，否则 Etcher 将格式化被选中的磁盘，造成重要数据丢失！
:::

<div style={{textAlign: 'center'}}>
  <img src="/img/rock4/4d/etcher-02.webp" style={{width: '100%', maxWidth: '1200px'}} />
</div>

① ： 选择需要安装系统镜像的磁盘设备

② ： 点击 `Select 1` 选项确认设备选择

<div style={{textAlign: 'center'}}>
  <img src="/img/rock4/4d/etcher-03.webp" style={{width: '100%', maxWidth: '1200px'}} />
</div>

3.开始写入系统镜像：点击 `Flash` 选项，等待软件自动进行系统镜像的写入和校验。

<div style={{textAlign: 'center'}}>
  <img src="/img/rock4/4d/etcher-04.webp" style={{width: '100%', maxWidth: '1200px'}} />
</div>

<div style={{textAlign: 'center'}}>
等待系统写入完成
  <img src="/img/rock4/4d/etcher-05.webp" style={{width: '100%', maxWidth: '1200px'}} />
</div>

<div style={{textAlign: 'center'}}>
等待系统校验完成
  <img src="/img/rock4/4d/etcher-07.webp" style={{width: '100%', maxWidth: '1200px'}} />
</div>

4.成功写入系统镜像后，关闭 Etcher 软件！

## 系统信息

您使用我们提供的系统镜像，首次需要使用我们设置的用户名和密码登录系统。

- radxa

用户账号：radxa

用户密码：radxa
