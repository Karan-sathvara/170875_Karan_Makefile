target:	build	run	clean

DEBUG = 1
CC = gcc
CFLAGS = -Wall

ifeq ($(DEBUG),1)
	CFLAGS += -g -O0
else
	CFLAGS += -O3
endif

PROJECTS := $(wildcard project*)
SRC := $(wildcard project*/*.c)
OBJ := $(SRC:.c=.o)

build: $(OBJ)
	@for project in $(PROJECTS); do \
		$(CC) $(CFLAGS) $$project/*.o -o $$project/$$project.out; \
	done

%.o: %.c
	$(CC) $(CFLAGS) -c $< -o $@

run: build
	@for project in $(PROJECTS); do \
		./$$project/$$project.out; \
	done

clean:
	rm -f project*/*.o project*/*.out
