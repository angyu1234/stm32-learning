# 第 1 周 · 环境跑通，第一颗 LED 亮起来

| 日期 | 目录 | 内容 |
|---|---|---|
| D3 | `d03_led_hal/` | CubeMX + HAL 点亮 PC13 |
| D4 | `d04_led_register/` | 纯寄存器方式点亮 PC13（**本周重点**） |

## 操作说明

CubeIDE 工程不要整个目录一股脑提交（`Debug/` 会被 `.gitignore` 拦掉，这是对的）。
需要提交的是：`.ioc`、`Core/`、`Drivers/`（HAL 库可以只保留用到的）、`.project`、`.cproject`。

如果觉得工程太大，也可以只提交**自己写的 `.c` / `.h` 文件**，并在目录下放一个 `README.md` 说明 CubeMX 的配置参数（时钟、引脚、外设）。两种方式都行，前后保持一致即可。

## D4 需要提交的关键文件

```
d04_led_register/
├── Core/Src/main.c          # 寄存器初始化与主循环，含详细注释
├── Core/Inc/main.h
├── *.ioc                    # CubeMX 配置（务必提交）
└── README.md                # 说明：哪个函数替代了 HAL、寄存器地址从哪来
```

## 本周视频

见 [`../videos/README.md`](../videos/README.md) 的 W01-D03 / W01-D04 / W01-D06 / W01-WEEK。

## D4 讲解视频要回答的四个问题

1. 为什么必须先使能 RCC 的 IOPC 时钟？
2. PC13 为什么配置在 `CRH` 而不是 `CRL`？对应哪几位？
3. 那 4 个配置位的值（MODE / CNF）是怎么算出来的？
4. 为什么推荐用 `BSRR` 而不是直接写 `ODR`？

能流畅答完这四个问题，D4 就过关了。
