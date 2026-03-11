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

SOURCES = $(wildcard *.c)
TARGET = project1.out
OBJECTS = $(SOURCES:.c=.o)

build: $(OBJECTS)
	$(CC) $(OBJECTS) -o $(TARGET) $(LDFLAGS)

%.o: %.c
	$(CC) $(CFLAGS) -c $< -o $@

run: build
	./$(TARGET)

clean:
	rm -f *.o $(TARGET)
