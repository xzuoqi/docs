---
sidebar_position: 3
---

import USBSystem from '../../../../../common/radxa-os/install-system/qualcomm/\_usb_flash_system.mdx';

# 线刷系统镜像到 UFS

介绍使用双头 USB Type-A 数据线给主板刷入 UFS 系统镜像。

## 使用前提

1. 将 UFS 模块安装到主板的 eMMC & UFS 二合一卡槽

2. 使主板进入 EDL 模式并使用双头 USB Type-A 数据线连接主板和电脑 --> 可参考 [进入 EDL 模式](./edl_mode.md) 教程

3. 配置 EDL 工具环境 --> 可参考 [使用 EDL 工具](./set_edl_variable.md) 教程

<USBSystem download_page="../../../download" board="dragon-q6a" spi_path="\flat_build\spinor\dragon-q6a\" loader="prog_firehose_ddr.elf" storage_type="ufs" start_sector="0" image_file="radxa-dragon-q6a_noble_kde_t4.output_4096.img"/>
