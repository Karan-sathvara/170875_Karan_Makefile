Target: build1	build2	build3	run1	run2	run3	clean

DEBUG = 1
CC = gcc
CFLAGS = -Wall -g
LDFLAGS =

ifeq ($(DEBUG),1)
	CFLAGS += -O0
else
	CFLAGS += -O3
endif

build1: src1.c
	$(CC) $(CFLAGS) src1.c -o bin1

build2: src2.c
	$(CC) $(CFLAGS) src2.c -o bin2

build3: src3.c
	$(CC) $(CFLAGS) src3.c -o bin3

run1: build1
	./bin1

run2: build2
	./bin2

run3: build3
	./bin3

clean:
	rm -f bin1 bin2 bin3
