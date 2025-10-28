---
sidebar_position: 3
---

# USB Type-C 接口

瑞莎 ROCK 4D 支持 USB Type-C 和 GPIO 供电，我们推荐使用 USB Type-C 接口进行供电，仅支持 5V 电源输入，建议电流 3A 以上，确保所有外设稳定运行。

我们推荐使用支持 PD 协议的标准 5V Type-C 电源适配器进行供电。

<div style={{textAlign: 'center'}}>
  <img src="/img/rock4/4d/rock4d-typec.webp" style={{width: '100%', maxWidth: '1200px'}} />
</div>

:::tip

参考电源：

- [瑞莎 PD 30W电源适配器(推荐使用)](https://radxa.com/products/accessories/power-pd-30w)

- 标准 Type-C 电源适配器( 5V 电源输入，支持 PD 协议，建议电流 3A 以上)

:::

## 使用指南

可以通过 ROCK 4D 的板载指示灯判断是否供电成功，如果供电成功，指示灯会亮起。

## 接口规格

:::tip
详细接口规格参考下载专区的 [硬件设计 : 原理图](../download)
:::

| Pin# | Name | Pin#  | Name    | Pin# | Name | Pin# | Name |
| :--: | :--- | :---: | :------ | :--: | :--- | :--: | :--- |
|  1   | GND  |   7   | NC      |  A5  | GND  |  A7  | NC   |
|  2   | GND  | A1B12 | GND     |  B5  | GND  |  B7  | NC   |
|  3   | GND  | B1A12 | GND     |  A6  | NC   |  A8  | NC   |
|  4   | GND  | A4B9  | DCIN_5V |  B6  | NC   |  B8  | NC   |
|  6   | NC   | B4A9  | DCIN_5V |      |      |      |      |
