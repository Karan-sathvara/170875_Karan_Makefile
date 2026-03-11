Target: build   run     clean

DEBUG = 1
CC = gcc
CFLAGS = -Wall
LDFLAGS =

ifeq ($(DEBUG),1)
        CFLAGS += -g -O0
else
        CFLAGS += -O3
endif

SOURCES = $(wildcard *.c project*/*.c)
OBJECTS = $(SOURCES:.c=.o)
TARGET = final.out

build: $(OBJECTS)
	$(CC) $(OBJECTS) -o $(TARGET)

%.o: %.c function.h
	$(CC) $(CFLAGS) -c $< -o $@

run: build
	./$(TARGET)

clean:
	rm -f $(OBJECTS) $(TARGET)
