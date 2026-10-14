# blink_led · D13~D14 CubeIDE 工程

第一个 STM32 工程：配置 SYS Debug = Serial Wire + 一个 GPIO 输出，点亮 PC13 板载 LED。

## CubeIDE 工程该提交哪些文件

**不要**把整个工程目录一股脑提交（`Debug/` 会被 `.gitignore` 拦掉，这是对的）。
需要提交的是：

```
blink_led/
├── Core/Src/main.c          # 用户代码，含详细注释
├── Core/Inc/main.h
├── Drivers/                 # HAL 库（可只保留用到的部分）
├── *.ioc                    # CubeMX 配置，务必提交
├── .project
├── .cproject
└── README.md                # 本文件
```

也可以只提交自己写的 `.c` / `.h`，并在这里写明 CubeMX 的配置参数（时钟、引脚、外设）。两种方式都行，**前后保持一致即可**。

## 配置要点

| 项 | 值 | 为什么 |
|---|---|---|
| MCU | STM32F103C8 | — |
| SYS → Debug | **Serial Wire** | 不设会导致**第二次下载失败** |
| GPIO | PC13 Output Push-Pull | 板载 LED |
| 时钟 | HCLK 72MHz | F103 常规配置 |

## D14 讲解视频要回答的四个问题

1. 为什么必须先使能 RCC 的 IOPC 时钟？
2. PC13 为什么配置在 `CRH` 而不是 `CRL`？对应哪几位？
3. 那 4 个配置位（MODE / CNF）的值是怎么算出来的？
4. 为什么推荐用 `BSRR` 而不是直接写 `ODR`？

能流畅答完这四个，D14 就过关了。
