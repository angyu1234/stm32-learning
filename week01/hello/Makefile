CC      = gcc
CFLAGS  = -Wall -Wextra -g
TARGET  = hello

all: $(TARGET)

$(TARGET): hello.c
	$(CC) $(CFLAGS) -o $(TARGET) hello.c

clean:
	rm -f $(TARGET)

.PHONY: all clean
