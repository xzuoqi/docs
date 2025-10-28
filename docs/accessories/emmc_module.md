---
sidebar_position: 5
---

# 瑞莎 eMMC 模块

Radxa eMMC 模块采用eMMC 5.1规范，提供四种容量选择： 16g / 32g / 64g / 128g。同时，你可以选择支持工业级长寿命的型号。此外，该模块支持JEDEC的标准eMMC命令集，并为高速读写而设计，使数据传输更快。

![eMMC Module](/img/accessories/emmc-module.webp)

## 读 / 写速度测试

我们使用的eMMC芯片的是Foresee，由深圳嵌入式存储公司Longsys生产，他们在2017年收购了Lexar品牌。

下面是我们对不同品牌的eMMC芯片做的测试。

| Capacity | Brand       | Read    | Write    |
| -------- | ----------- | ------- | -------- |
| 8G       | Sandisk     | 270MB/s | 39.4MB/s |
| 16G      | Sandisk     | 230MB/s | 79.6MB/s |
| 16G      | Kingston    | 160MB/s | 50.1MB/s |
| 16G      | **Foresee** | 189MB/s | 74.4MB/s |
| 16G      | **Foresee** | 241MB/s | 79.5MB/s |
| 32G      | Sandisk     | 263MB/s | 139MB/s  |
| 32G      | Samsung     | 263MB/s | 78.3MB/s |
| 32G      | Kingston    | 152MB/s | 87.2MB/s |
| 64G      | Sandisk     | 207MB/s | 100MB/s  |
| 64G      | **Foresee** | 215MB/s | 148MB/s  |
| 64G      | **Foresee** | 194MB/s | 148MB/s  |
| 128G     | Toshiba     | 217MB/s | 143MB/s  |

## 接口规格

- JEDEC 标准: v5.1
- B2B连接器规格： GB042-34S-H10（插座-34针）+ GB042-30S-H10（插座-30针）
- 存储选项：16G / 32G / 64G / 128G
- 兼容性: 兼容 ROCK 3A / 3B / 3C / 4A / 4B / 4C / 4C PLUS / 4D\* / 4SE / 5A / 5B
- 尺寸：13mm x 18mm x 1.5mm

> 注意：因为引脚复用关系，ROCK 4D 带 SPI Flash 的 版本不支持 eMMC 模块。

[**购买链接**](https://radxa.com/products/accessories/emmc-module#buy)

## 引脚说明

### GB042-34S-H10（插座-34针）

主要用于信号传输。

| Signal      | Pin | Pin | Signal   |
| ----------- | --- | --- | -------- |
| GND         | 1   | 18  | GND      |
| EMMC D5     | 2   | 19  | GND      |
| GND         | 3   | 20  | VCC 1V8  |
| EMMC D4     | 4   | 21  | VCC 1V8  |
| GND         | 5   | 22  | VCC 3V3  |
| EMMC D0     | 6   | 23  | VCC 3V3  |
| GND         | 7   | 24  | GND      |
| EMMC CLK    | 8   | 25  | EMMC CMD |
| GND         | 9   | 26  | GND      |
| EMMC D3     | 10  | 27  | EMMC D2  |
| GND         | 11  | 28  | GND      |
| VCC 1V8     | 12  | 29  | EMMC D1  |
| GND         | 13  | 30  | GND      |
| GND         | 14  | 31  | EMMC D7  |
| EMMC STROBE | 15  | 32  | GND      |
| GND         | 16  | 33  | EMMC D6  |
| GND         | 17  | 34  | GND      |

### GB042-30S-H10（插座-30针）

主要用于机械固定和支撑。
