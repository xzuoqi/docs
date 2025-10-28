---
sidebar_position: 2
---

# Resource Download

## Hardware Design

Orion O6 V1.2 Version

[V1.2 Schematic pdf](https://dl.radxa.com/orion/o6/hw/radxa_orion_o6_v1.20_schematic.pdf)

[V1.2 Components Placement Map Bottom pdf](https://dl.radxa.com/orion/o6/hw/radxa_orion_o6_v1.20_Components_Placement_map_bot.pdf)

[V1.2 Components Placement Map Top pdf](https://dl.radxa.com/orion/o6/hw/radxa_orion_o6_v1.20_Components_Placement_map_top.pdf)

## BIOS

| Download Link                                                                             | Format | Description                                                                                                                                                                                                                                                                          |
| ----------------------------------------------------------------------------------------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| [Radxa DL](https://dl.radxa.com/orion/o6/images/bios/orion-o6-bios-0.3.0-1.zip)           | zip    | Version 0.3.0-1                                                                                                                                                                                                                                                                      |
| [Github Release](https://github.com/radxa-pkg/edk2-cix/releases/latest)                   | deb    | The BIOS content is located within the `edk2-cix_*_all.deb` package. This file can be opened with 7-Zip on Windows, KDE Ark on Linux, and extracted using the `ar -x` command on macOS. Inside the package, the path to the BIOS file is `data.tar.xz/usr/share/edk2/radxa/orion-o6` |
| [Radxa DL](https://dl.radxa.com/orion/o6/images/bios/SystemReady/latest/orion-o6-bios.7z) | 7z     | Version 9.0.0, Arm SystemReady Certification BIOS                                                                                                                                                                                                                                    |

### BIOS Compatibility Instructions

Different versions of BIOS contain different memory initialization codes. If an older version of BIOS is installed on newer version hardware, the system may fail to start.

O6 comes pre-installed with a BIOS that is compatible with its hardware. We do not recommend downgrading to a version older than the pre-installed BIOS.

For the value of "Memory Chip Raw Value" in the following table, please refer to the corresponding value in `Device Manager - System Information - Memory Chip` within the BIOS settings.

| Memory Chip Raw Value | Description     | Supported Versions                                                                                            |
| --------------------- | --------------- | ------------------------------------------------------------------------------------------------------------- |
| 0                     | 4 GiB           | Any                                                                                                           |
| 2                     | 2 GiB           | 0.2.0-1 and above                                                                                             |
| 5                     | 3 GiB           | Any                                                                                                           |
| 7                     | 6 GiB           | Reserved configuration                                                                                        |
| 8                     | 8 GiB           | Any                                                                                                           |
| 9                     | 12 GiB          | Reserved configuration                                                                                        |
| 10                    | 16 GiB (Hynix)  | Any                                                                                                           |
| 11                    | 8 GiB           | 0.2.0-1 and above                                                                                             |
| 12                    | 16 GiB (Rayson) | [0.3.1-1](https://github.com/radxa-pkg/edk2-cix/releases/download/0.3.1-1/edk2-cix_0.3.1-1_all.deb) and above |

:::info
The current memory compatibility of SystemReady BIOS is equivalent to 0.2.0-1.
:::

## Debian 12 pre‑installed image

### Debian12 Desktop b6

|                                 orion-o6-debian12-preinstalled-desktop-b6.img                                 |
| :-----------------------------------------------------------------------------------------------------------: |
| [Radxa DL Link](https://dl.radxa.com/orion/o6/images/debian/orion-o6-debian12-preinstalled-desktop-b6.img.gz) |
|                   [BaiduPan Link](https://pan.baidu.com/s/1BKqR3Q67c580ZgjnllL7Ow?pwd=w2ex)                   |
|            [Mega Link](https://mega.nz/file/x34WzQQC#UOyVPHcdMMYdSdYUsYQb2K-fWE8Zsa13QbTiLVvkIJ4)             |

NOTE:

- It is for NVME SSD and USB boot.
- Users can write the image to a USB flash drive or NVME SSD through balenaEtcher on the host PC.

| Username | Password |
| :------: | :------: |
|  radxa   |  radxa   |

### Debian12 Desktop ISO b6

|                                 orion-o6-debian12-desktop-arm64-b6.iso                                 |
| :----------------------------------------------------------------------------------------------------: |
| [Radxa DL Link](https://dl.radxa.com/orion/o6/images/debian/orion-o6-debian12-desktop-arm64-b6.iso.gz) |
|               [BaiduPan Link](https://pan.baidu.com/s/1WSrdcqFUXlkkAsvbQtVh6A?pwd=nnyi)                |
|         [Mega Link](https://mega.nz/file/kyoHkRRT#86E73AN0-bGb01mkC-U30hPBhZMabJa7Dbgcf5U2a5w)         |

NOTE:

- The image is used for USB boot disk. Users can install the system to NVME SSD through this USB boot disk.
- Users can write the image to the USB disk through balenaEtcher on the host PC.
- Please record the passwords of the root user and ordinary user during the installation process.

### RadxaOS

:::info
RadxaOS is still in the testing phase. Compared with the above systems, there may be some functional deficiencies.

Known issues of T1:

1. Chromium cannot be started during the first boot: Debian issue [#1035061](https://bugs-devel.debian.org/cgi-bin/bugreport.cgi?bug=1035061).
2. Currently, the NPU userspace is not pre-installed in the system, and the system is not compatible with the CIX EBP 25Q1 NPU driver package.
3. The throughput of the 5GbE is relatively low.
4. The suspend and wake-up functions do not work properly.

:::

[Download Link](https://github.com/radxa-build/orion-o6/releases/download/rsdk-t1/orion-o6_bookworm_gnome_t1.output.img.xz)

## Fedora

[Fedora 41 Gnome](https://openkoji.iscas.ac.cn/pub/dist-repos/dl/Radxa/Orion-O6/images/fedora-disk-gnome-workstation_radxa_orion-o6_202501041239.raw.gz)

| Username | Password |
| :------: | :------: |
|   root   | aarch64  |

## Android

[Android 14 RC2 20250903 system image](https://github.com/radxa/cix-android-manifests/releases/download/radxa-orion-o6-android14-rc2-20250903/Radxa_Orion_O6_Android14_RC2_20250903_images.zip)

[Android BIOS 0.0.1 version image](https://github.com/radxa/cix-android-manifests/releases/download/radxa-orion-o6-android14-rc2-20250903/orion-o6-bios-android-0.0.1.zip)

## Openharmony

[Openharmony 20251016 image](https://github.com/radxa/cix-openharmony-manifests/releases/download/radxa-orion-o6-Harmony-20251016-v1.0/ohos_images.zip)

[Openharmony BIOS v1.0 image](https://github.com/radxa/cix-openharmony-manifests/releases/download/radxa-orion-o6-Harmony-20251016-v1.0/ohos_bios.zip)
