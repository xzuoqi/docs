---
sidebar_position: 2
---

# 无屏模式

无屏模式是指瑞莎 ROCK 4D 不接显示屏，通过串口/ SSH / VNC 控制开发板，适合有一定开发经验的用户使用。

具体控制思路 : 通过串口调试的方法获取 ROCK 4D 的 IP 地址，然后配置好对应的 SSH 和 VNC 环境，进一步通过 SSH 或 VNC 远程登录 ROCK 4D 进行控制。

:::tip

- 串口调试 : 详细步骤参考 [串口调试](./uart_debug) 教程
- SSH 远程登录 : 详细步骤参考 [远程登录](./ssh-remote) 教程
- VNC 远程登录 : 详细步骤参考 [VNC远程登录](./vnc-remote) 教程
  :::

## 准备工作

可以按照 [串口调试](./uart_debug) 和 [远程登录](./remote-login) 教程连接 ROCK 4D。

## 控制界面

无屏模式下的串口/ SSH控制是命令行模式，VNC控制是图形界面模式。

### 命令行模式

串口控制需要依赖数据线，而 SSH 控制不需要依赖数据线，只需要保证设备在同一局域网下。

① ： 打开 Linux 终端，通过串口方式登录 ROCK 4D

② ： 打开 Linux 终端，通过 SSH 方式登录 ROCK 4D

<div style={{textAlign: 'center'}}>
    <img src="/img/rock4/4d/nodiplay-login.webp" style={{width: '100%', maxWidth: '1200px'}} />
</div>

### 图形界面模式

VNC 控制需要保证控制和被控设备都处于同一局域网下。

<div style={{textAlign: 'center'}}>
VNC远程登录成功
    <img src="/img/rock4/4d/vnc-connect-03.webp" style={{width: '100%', maxWidth: '1200px'}} />
</div>
