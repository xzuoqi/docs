---
sidebar_position: 5
---

# 资源下载汇总

## 硬件设计

## 刷机工具

- [Zagdig](https://zadig.akeo.ie/)：Windows Maskrom 驱动。
- [RZ USB Boot Helper](https://dl.radxa.com/zero/tools/windows/RZ_USB_Boot_Helper_V1.0.0.zip)：Windows bootloader 加载工具。
- [radxa-zero2-2pro-erase-emmc.bin](https://dl.radxa.com/zero2pro/images/loader/radxa-zero-2pro-erase-emmc.bin)：自动擦除 eMMC，然后将 eMMC 作为 USB 存储设备显示。这是加载新 Linux 映像的推荐方法。
- [rz-2pro-fastboot-loader.bin](https://dl.radxa.com/zero2pro/images/loader/rz-2pro-fastboot-loader.bin)：启用 fastboot 模式。其不能用于安装我们的官方 Android 系统。
- [rz-2pro-udisk-loader.bin](https://dl.radxa.com/zero2pro/images/loader/rz-2pro-udisk-loader.bin): 将板载 eMMC 作为 USB 大容量存储设备。
- [u-boot.bin](https://dl.radxa.com/zero2pro/images/loader/u-boot.bin)：用于 USB 启动的主线 U-Boot 引导加载器。如果刷写到 eMMC/microSD，则无法工作。
- [u-boot.bin.sd.bin](https://dl.radxa.com/zero2pro/images/loader/u-boot.bin.sd.bin)：用于 eMMC/microSD 启动的主线 U-Boot 引导加载程序。

## 操作系统镜像

- [Android TV](https://github.com/radxa/manifests/releases/download/Radxa-zero2pro-20240119/zero2-fastboot-flashall-20240118.zip)

:::caution
除了上面的镜像经过官方充分测试外，其他镜像未经过严格测试，可能会存在未知问题，仅用于评估使用。
:::

<!-- 更多镜像请查看： [第三方系统镜像](../other-os/3rd-images) -->

<!-- ## 质量认证

- [CE RED - EU](https://dl.radxa.com/zero/docs/compliance/radxa_zero_ce_red_report.zip)
- [FCC ID - US](https://fccid.io/2A3PA-RADXA-ZERO) -->
