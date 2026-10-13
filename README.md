# stm32-learning

STM32 嵌入式学习记录 —— 从零基础到嵌入式软件工程师岗位。

> 学习周期：52 周 / 约 620 小时 · 主线 STM32F103 + FreeRTOS + Linux 驱动
> 平台：STM32F103C8T6 最小系统板 · 工具链：STM32CubeIDE + ST-Link V2

## 仓库用途

这个仓库不是「代码备份」，而是**能力证明**。它记录了每个知识点的实现代码、每段原理的讲解视频、以及每次踩坑的过程。面试时它会替我说明：这些东西是我一步一步真正做出来的。

## 目录说明

| 目录 | 内容 |
|---|---|
| `docs/` | 交付物规范、系统框图、截图 |
| `notes/` | 学习笔记（含笔记索引、寄存器速查表、面试速答） |
| `videos/` | 视频链接汇总（视频文件本身用网盘/B站存放，见 `videos/README.md`） |
| `week01/` | 第 1 周：环境搭建、HAL 与寄存器点亮 LED |
| `week02/` | 第 2 周：C 语言指针与内存内功 |
| `weekNN/` | 后续周次按此规律扩展 |

## 学习进度

完整打卡表见 [PROGRESS.md](./PROGRESS.md)。

- [ ] 第 1 周 · 环境搭建 + HAL/寄存器点灯
- [ ] 第 2 周 · C 语言指针与内存
- [ ] 第 3 周起 · STM32 外设逐个攻破（GPIO / 中断 / 定时器 / 串口 / I²C / SPI / ADC / DMA）

## 技术栈

`C` · `STM32F103 (Cortex-M3)` · `STM32CubeIDE` · `HAL + 寄存器混合编程` · `FreeRTOS`（后续） · `Linux 设备驱动`（后续）

## 视频讲解

所有讲解视频的链接集中在 [videos/README.md](./videos/README.md)。

## 提交规范

```
<类型>(范围): <简短描述>

feat 新功能 / fix 修 bug / docs 文档 / refactor 重构 / chore 杂项
```

示例：`feat(week01): 用寄存器方式点亮 PC13 LED`

---

*个人学习仓库，欢迎交流。*
