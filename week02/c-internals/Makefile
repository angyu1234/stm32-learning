# 第 2 周 C 语言内功练习
# 用法：make   编译全部 .c 文件
#       ./exercises   运行自测题
#       make clean    清理

CC     := gcc
CFLAGS := -Wall -Wextra -std=c11 -g -O0
SRCS   := $(wildcard *.c)
BINS   := $(SRCS:.c=)

.PHONY: all clean run

all: $(BINS)

# 每个 .c 编译成同名可执行文件
%: %.c
	$(CC) $(CFLAGS) -o $@ $<

run: exercises
	./exercises

clean:
	$(RM) $(BINS)
