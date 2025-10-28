---
sidebar_position: 4
---

# Hardware interface description

## Interface overview

<img src="../../../img/rock3/3a/rock3a-interfaces.webp" width="800" alt="rock 3a interfaces" />

## Power

Support QC 3.0/2.0 adapter, 9V/2A, 12V/1.5A

## Debug Serial Port

## Ethernet Port

## 40 PIN GPIO Header

### GPIO voltage

Voltage Range

| Type | Voltage | Tolerance |
| ---- | ------- | --------- |
| GPIO | 3.3V    | 3.63V     |
| ADC  | 1.8V    | 1.98V     |

### GPIO interface

ROCK 3A provides a 40pin GPIO socket, which is compatible with most sensor applications on the market.

:::caution
Tip: Actual compatibility is subject to actual usage.
:::

<Tabs queryString="revision">
<TabItem value="v1_3" label="v1.3+">
   <div className='gpio_style' style={{ overflow :"auto"}}  >

| GPIO number |  Function4  |  Function3   |  Function2  |  Function1  |               Pin#               |              Pin#               | Function1 |                 Function2                 |  Function3  |  Function4  | GPIO number |
| ----------- | :---------: | :----------: | :---------: | :---------: | :------------------------------: | :-----------------------------: | :-------: | :---------------------------------------: | :---------: | :---------: | ----------- |
|             |             |              |             |    +3.3V    | <div className='yellow'>1</div>  |  <div className='red'>2</div>   |   +5.0V   |                                           |             |             |             |
| 32          | CAN1_RX_M0  | UART3_RX_M0  | I2C3_SDA_M0 |  GPIO1_A0   |  <div className='green'>3</div>  |  <div className='red'>4</div>   |   +5.0V   |                                           |             |             |             |
| 33          | CAN1_TX_M0  | UART3_TX_M0  | I2C3_SCL_M0 |  GPIO1_A1   |  <div className='green'>5</div>  | <div className='black'>6</div>  |    GND    |                                           |             |             |             |
| 13          |             |   PWM1_M1    | I2C2_SCL_M0 |  GPIO0_B5   |  <div className='green'>7</div>  | <div className='green'>8</div>  | GPIO0_D1  | <div className='orange'>UART2_TX_M0</div> |             |             | 25          |
|             |             |              |             |     GND     |  <div className='black'>9</div>  | <div className='green'>10</div> | GPIO0_D0  | <div className='orange'>UART2_RX_M0</div> |             |             | 24          |
| 116         |             | UART7_TX_M1  |  PWM14_M0   |  GPIO3_C4   | <div className='green'>11</div>  | <div className='green'>12</div> | GPIO3_A3  |                                           |             |             | 99          |
| 117         |             | UART7_RX_M1  | PWM15_IR_M0 |  GPIO3_C5   | <div className='green'>13</div>  | <div className='black'>14</div> |    GND    |                                           |             |             |             |
| 16          |             |   UART0_RX   |   PWM1_M0   |  GPIO0_C0   | <div className='green'>15</div>  | <div className='green'>16</div> | GPIO0_B6  |                I2C2_SDA_M0                |   PWM2_M1   |             | 14          |
|             |             |              |             |    +3.3V    | <div className='yellow'>17</div> | <div className='green'>18</div> | GPIO3_B2  |                UART4_TX_M1                |   PWM9_M0   |             | 106         |
| 147         | CAN1_TX_M1  | SPI3_MOSI_M1 | PWM15_IR_M1 |  GPIO4_C3   | <div className='green'>19</div>  | <div className='black'>20</div> |    GND    |                                           |             |             |             |
| 149         | UART9_TX_M1 | SPI3_MISO_M1 |  PWM12_M1   |  GPIO4_C5   | <div className='green'>21</div>  | <div className='green'>22</div> | GPIO0_C1  |                  PWM2_M0                  |  UART0_TX   |             | 17          |
| 146         | CAN1_RX_M1  | SPI3_CLK_M1  |  PWM14_M1   |  GPIO4_C2   | <div className='green'>23</div>  | <div className='green'>24</div> | GPIO4_C6  |                 PWM13_M1                  | SPI3_CS0_M1 | UART9_RX_M1 | 150         |
|             |             |              |             |     GND     | <div className='black'>25</div>  | <div className='green'>26</div> | GPIO4_D1  |                SPI3_CS1_M1                |             |             | 153         |
| 12          |   USB_DP    |  CAN0_RX_M0  |  I2C1_SDA   |  GPIO0_B4   |  <div className='blue'>27</div>  | <div className='blue'>28</div>  | GPIO0_B3  |                 I2C1_SCL                  | CAN0_TX_M0  |   USB_DM    | 13          |
| 95          |             |              | UART8_TX_M1 |  GPIO2_D7   | <div className='green'>29</div>  | <div className='black'>30</div> |    GND    |                                           |             |             |             |
| 96          |             |              | UART8_RX_M1 |  GPIO3_A0   | <div className='green'>31</div>  | <div className='green'>32</div> | GPIO3_C2  |                UART5_TX_M1                |             |             | 114         |
| 115         |             | UART5_RX_M1  | SPI1_CLK_M1 |  GPIO3_C3   | <div className='green'>33</div>  | <div className='black'>34</div> |    GND    |                                           |             |             |             |
| 100         |             |              |             |  GPIO3_A4   | <div className='green'>35</div>  | <div className='green'>36</div> | GPIO3_A2  |                                           |             |             | 98          |
|             |             |              |             | SARADC_VIN5 | <div className='green'>37</div>  | <div className='green'>38</div> | GPIO3_A6  |                                           |             |             | 102         |
|             |             |              |             |     GND     | <div className='black'>39</div>  | <div className='green'>40</div> | GPIO3_A5  |                                           |             |             | 101         |

</div>

### More details about 40-pin Header In V1.3+

- Pins marked with color orange are designed for debug console.
- PWM: x7, PWM1 / PWM2 / PWM9 / PWM12 / PWM13 / PWM14 / PWM15
- SPI: x1, SPI3
- I2C: x3, I2C1 / I2C2 / I2C3
- UART: x6, UART0 / UART3 / UART5 / UART7 / UART8 / UART9
- ADC: x1, SARADC_VIN5
- CAN: x2, CAN0 / CAN1
- USB 2.0: x1, USB_DP(PIN#27) + USB_DM(PIN#28)
  - When we select this USB function, you need to modify the hardware like this:
  - -> Remove R90526 R90527
  - -> Add R90536 R90537

</TabItem>
<TabItem value="v1_2" label="v1.2">
   <div className='gpio_style' style={{ overflow :"auto"}}  >

| GPIO number |  Function4  |  Function3   |  Function2  | Function1 |               Pin#               |              Pin#               | Function1 |                 Function2                 |  Function3  |  Function4  | GPIO number |
| ----------- | :---------: | :----------: | :---------: | :-------: | :------------------------------: | :-----------------------------: | :-------: | :---------------------------------------: | :---------: | :---------: | ----------- |
|             |             |              |             |   +3.3V   | <div className='yellow'>1</div>  |  <div className='red'>2</div>   |   +5.0V   |                                           |             |             |             |
| 32          | CAN1_RX_M0  | UART3_RX_M0  | I2C3_SDA_M0 | GPIO1_A0  |  <div className='green'>3</div>  |  <div className='red'>4</div>   |   +5.0V   |                                           |             |             |             |
| 33          | CAN1_TX_M0  | UART3_TX_M0  | I2C3_SCL_M0 | GPIO1_A1  |  <div className='green'>5</div>  | <div className='black'>6</div>  |    GND    |                                           |             |             |             |
| 111         |             | UART3_TX_M1  |  PWM12_M0   | GPIO3_B7  |  <div className='green'>7</div>  | <div className='green'>8</div>  | GPIO0_D1  | <div className='orange'>UART2_TX_M0</div> |             |             | 25          |
|             |             |              |             |    GND    |  <div className='black'>9</div>  | <div className='green'>10</div> | GPIO0_D0  | <div className='orange'>UART2_RX_M0</div> |             |             | 24          |
| 116         |             | UART7_TX_M1  |  PWM14_M0   | GPIO3_C4  | <div className='green'>11</div>  | <div className='green'>12</div> | GPIO3_A3  |                                           |             |             | 99          |
| 117         |             | UART7_RX_M1  | PWM15_IR_M0 | GPIO3_C5  | <div className='green'>13</div>  | <div className='black'>14</div> |    GND    |                                           |             |             |             |
| 16          |             |   UART0_RX   |   PWM1_M0   | GPIO0_C0  | <div className='green'>15</div>  | <div className='green'>16</div> | GPIO3_A1  |                                           |             |             | 97          |
| 17          |             |   UART0_TX   |   PWM2_M0   | GPIO0_C1  | <div className='yellow'>17</div> | <div className='green'>18</div> | GPIO3_B2  |                UART4_TX_M1                |   PWM9_M0   |             | 106         |
| 147         | CAN1_TX_M1  | SPI3_MOSI_M1 | PWM15_IR_M1 | GPIO4_C3  | <div className='green'>19</div>  | <div className='black'>20</div> |    GND    |                                           |             |             |             |
| 149         | UART9_TX_M1 | SPI3_MISO_M1 |  PWM12_M1   | GPIO4_C5  | <div className='green'>21</div>  | <div className='green'>22</div> |  ADC_IN5  |                                           |             |             |             |
| 146         | CAN1_RX_M1  | SPI3_CLK_M1  |  PWM14_M1   | GPIO4_C2  | <div className='green'>23</div>  | <div className='green'>24</div> | GPIO4_C6  |                 PWM13_M1                  | SPI3_CS0_M1 | UART9_RX_M1 | 150         |
|             |             |              |             |    GND    | <div className='black'>25</div>  | <div className='green'>26</div> | GPIO4_D1  |                SPI3_CS1_M1                |             |             | 153         |
| 14          |   USB_DP    |   PWM2_M1    | I2C2_SDA_M0 | GPIO0_B6  |  <div className='blue'>27</div>  | <div className='blue'>28</div>  | GPIO0_B5  |                I2C2_SCL_M0                |   PWM1_M1   |   USB_DM    | 13          |
| 95          |             |              | UART8_TX_M1 | GPIO2_D7  | <div className='green'>29</div>  | <div className='black'>30</div> |    GND    |                                           |             |             |             |
| 96          |             | UART8_RX_M1  | SPI2_CLK_M1 | GPIO3_A0  | <div className='green'>31</div>  | <div className='green'>32</div> | GPIO3_C2  |                UART5_TX_M1                |             |             | 114         |
| 115         |             |              | UART5_RX_M1 | GPIO3_C3  | <div className='green'>33</div>  | <div className='black'>34</div> |    GND    |                                           |             |             |             |
| 100         |             |              |             | GPIO3_A4  | <div className='green'>35</div>  | <div className='green'>36</div> | GPIO3_A2  |                                           |             |             | 98          |
| 112         |             | UART3_RX_M1  |  PWM13_M0   | GPIO3_C0  | <div className='green'>37</div>  | <div className='green'>38</div> | GPIO3_A6  |                                           |             |             | 102         |
|             |             |              |             |    GND    | <div className='black'>39</div>  | <div className='green'>40</div> | GPIO3_A5  |                                           |             |             | 101         |

</div>

### More details about 40-pin Header In V1.2

- Pins marked with color orange are designed for debug console.
- PWM: x7, PWM1 / PWM2 / PWM9 / PWM12 / PWM13 / PWM14 / PWM15
- SPI: x1, SPI3
- I2C: x2, I2C2 / I2C3
- UART: x6, UART0 / UART3 / UART5 / UART7 / UART8 / UART9
- ADC: x1, ADC_IN5
- CAN: x1, CAN1
- USB 2.0: x1, USB_DP(PIN#27) + USB_DM(PIN#28)
  - When we select this USB function, you need to modify the hardware like this:
  - -> Remove R90526 R90527
  - -> Add R90536 R90537

</TabItem>
</Tabs>

### USB Function Configuration on 40-Pin

On the ROCK 3A's 40-Pin interface, the following pins can be configured for USB 2.0:

- USB2_CON_DM: Pin number 28, resistor location R90537.
- USB3_CON_DP: Pin number 27, resistor location R90536.

By default, Pin-27 can be configured in software for functions such as GPIO0_B4 (see 40-Pin Pinout), while the USB3_CON_DP signal is not activated on the hardware. Pin-28 can be configured in software for functions such as GPIO0_B3 (see 40-Pin Pinout), and the USB2_CON_DM signal is also not activated on the hardware. To change these pins to USB functions, please follow the steps below to modify the reserved resistors:

- **Remove the 0-ohm resistors at R90526 and R90527.**
- **Solder 0-ohm resistors at R90537 and R90536.**

:::tip
The schematic and resistor locations can be viewed and downloaded from the hardware documentation.[Hardware Documentation Download](../getting-started/download)
:::

:::caution [Operation Note]

This procedure requires soldering skills, and it is recommended that it be performed by an experienced technician.

:::

## Bluetooth

## USB C OTG

## HDMI

## USB

## MIPI CSI

## MIPI DSI

## WIFI

## MicroSD
