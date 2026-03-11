target: build   run     clean

DEBUG = 1
CC = gcc
CFLAGS = -Wall

ifeq ($(DEBUG),1)
        CFLAGS += -g -O0
else
        CFLAGS += -O3
endif

PROJECTS := $(wildcard project*)

ROOT_SRC := $(wildcard *.c)
ROOT_OBJ := $(ROOT_SRC:.c=.o)
ROOT_VAR := main.out

SRC := $(wildcard project*/*.c)
OBJ := $(SRC:.c=.o)

PROJECT1_SRC := $(wildcard project1/*.c)
PROJECT1_OBJ := $(PROJECT1_SRC:.c=.o)

PROJECT2_SRC := $(wildcard project2/*.c)
PROJECT2_OBJ := $(PROJECT2_SRC:.c=.o)

PROJECT3_SRC := $(wildcard project3/*.c)
PROJECT3_OBJ := $(PROJECT3_SRC:.c=.o)
build: $(OBJ) $(ROOT_OBJ)
	$(CC) $(CFLAGS) $(ROOT_OBJ) -o main.out

	@for project in $(PROJECTS); do \
                $(CC) $(CFLAGS) $$project/*.o -o $$project/$$project.out; \
        done

project1: $(PROJECT1_OBJ)
	$(CC) $(CFLAGS) $(PROJECT1_OBJ) -o project1/main.out
	./project1/main.out

project2: $(PROJECT2_OBJ)
	$(CC) $(CFLAGS) $(PROJECT2_OBJ) -o project2/main.out
	./project2/main.out

project3: $(PROJECT3_OBJ)
	$(CC) $(CFLAGS) $(PROJECT3_OBJ) -o project3/main.out
	./project3/main.out

%.o: %.c
	$(CC) $(CFLAGS) -c $< -o $@

run: build
	./$(ROOT_VAR)
	@for project in $(PROJECTS); do \
                ./$$project/$$project.out; \
	done

clean:
	rm -f *.o main.out
	rm -f project*/*.o project*/*.out
