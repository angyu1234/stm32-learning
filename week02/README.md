# 第 2 周 · C 语言指针与内存内功

本目录下的代码**全部在 PC 上编译运行**（不需要 STM32 硬件）。

## 需要 gcc / make

你在 Linux 系统下直接装即可：

| 发行版 | 命令 |
|---|---|
| Ubuntu / Debian / Kali | `sudo apt update && sudo apt install build-essential` |
| Arch / Manjaro | `sudo pacman -S base-devel` |
| Fedora / RHEL | `sudo dnf groupinstall "Development Tools"` |
| openSUSE | `sudo zypper install -t pattern devel_basis` |

验证：`gcc --version` 和 `make --version` 都能输出版本号。

不想装也可以：把 `.c` 文件内容贴到 [godbolt.org](https://godbolt.org) 或 [onlinegdb.com](https://www.onlinegdb.com) 在线编译运行。

## 用法

```bash
cd week02/c-internals
make            # 编译目录下所有 .c 文件
./exercises     # 运行自测题（10 题）
make clean      # 清理
```

## 文件清单

| 文件 | 对应日期 | 内容 |
|---|---|---|
| `exercises.c` | D12 / D13 / D14 | **10 道自测题，带自动判分**。把 TODO 填完，全部 PASS 即本周过关 |
| `pointer_array.c` | D8 | 指针与数组：`a` / `&a` / `&a[0]`、退化、二维数组 |
| `cmd_parser.c` | D9 | 函数指针表驱动的命令解析器 |
| `const_ptr.c` | D10 | const 四种写法 + 多级指针 |
| `memory_layout.c` | D11 | 打印各类变量地址，验证内存布局 |
| `struct_align.c` | D13 | 5 个结构体的手算 sizeof 与 offsetof 验证 |
| `endian.c` | D13 | 两种方法判断大小端 + swap16 |

## 自测题说明

`exercises.c` 里每道题都有 `TODO` 注释。规则：

1. **先想再写**。特别是题目 5、6、7（结构体对齐），先在纸上算出来再写代码。
2. 全部填完后 `make && ./exercises`，看输出。
3. 目标是 **10 题全 PASS**（共 27 项检查）。
4. 卡住的题不要直接搜答案，去翻《C 和指针》或问人；实在不行记录下来，D12 缓冲日集中解决。

**参考答案**放在仓库之外（`week02-exercises-参考答案.c`），是刻意的：

- 这份仓库是给面试官看的，答案混在里面会让「这是你自己做的吗」变成疑问
- 参考答案已用 GCC 实测过，27 项全 PASS

真的卡死超过 40 分钟再看它，看完把对应知识点补进 `notes/面试速答-C语言内功.md`。

## D13 讲解视频要回答的问题

1. 在纸上画出 `struct { char a; int b; char c; }` 的 12 字节内存布局，标出填充位置
2. 讲清对齐的两条规则
3. 把成员重排后算出 8 字节，讲清为什么能省内存
4. 大小端的定义 + 两种判断方法
5. 什么时候必须用 `#pragma pack(1)`？举一个真实场景
