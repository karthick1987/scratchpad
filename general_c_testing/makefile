CC=gcc
CFLAGS= -I
OFLAGS = -O2
#STDFLAGS = -std=c++14
ifdef WFLAGS 
	echo $(WFLAGS)
	WFLAGS= -Werror -Wall
endif

SRC = $(wildcard *.c)
OBJS=$(subst .c,.o,$(SRC))

UNION_OBJS = union_test.o nodeID.o
CONST_OBJS = const_test.o
TEST_OBJS = test.o
PTR_OBJS = ptr.o
SORT_OBJS = sorting.o
SIGNAL_OBJS = signal_test.o

ptr: $(PTR_OBJS)
	$(CC) -g -o ptr $(PTR_OBJS)

test: $(TEST_OBJS)
	$(CC) -g -o test $(TEST_OBJS)

const_test: $(CONST_OBJS)
	$(CC) -o const_test $(CONST_OBJS)

union_test: $(UNION_OBJS)
	$(CC) -o union_test $(UNION_OBJS)

sort_test: $(SORT_OBJS)
	$(CC) -o sort_test $(SORT_OBJS)

signal_test: $(SIGNAL_OBJS)
	$(CC) -o signal_test $(SIGNAL_OBJS)

%.o: %.c
	$(CC) -g -c $(CFLAGS) $(STDFLAGS) $(OFLAGS) $< $(WFLAGS) -o $@
	@echo "CC $<"

clean:
	rm -rf *.o
