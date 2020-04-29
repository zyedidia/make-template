PROGRAMS = main
all: $(PROGRAMS)

ALLPROGRAMS = $(PROGRAMS)

include rules.mk

INCDIR = include
INC = $(INCDIR)
INC_PARAMS=$(foreach d, $(INC), -I$d)
CFLAGS += $(INC_PARAMS)

SRC = $(wildcard *.c)
OBJ = $(SRC:.c=.o)

%.o: %.c $(BUILDSTAMP)
	$(CC) $(CFLAGS) $(O) $(DEPCFLAGS) -o $@ -c $<

main: main.o
	$(CC) $(CFLAGS) $(LDFLAGS) $(O) -o $@ $^

# for inspecting assembly
%.s: %.c $(BUILDSTAMP)
	$(CC) $(CFLAGS) $(O) $(DEPCFLAGS) -o $@ -S $<

clean:
	rm -rf $(ALLPROGRAMS) *.o $(DEPSDIR)

format:
	clang-format -i $(SRC) $(wildcard $(INCLUDEDIR)/*.h)

.PHONY: all clean format
