PROGRAMS = main
all: $(PROGRAMS)

ALLPROGRAMS = $(PROGRAMS)

include rules.mk

INCLUDEDIR = include
INCLUDES = $(INCLUDEDIR)
CFLAGS += -I$(INCLUDES)

%.o: %.c $(BUILDSTAMP)
	$(CC) $(CFLAGS) $(O) $(DEPCFLAGS) -o $@ -c $<

main: main.o
	$(CC) $(CFLAGS) $(LDFLAGS) $(O) -o $@ $^

clean:
	rm -rf $(ALLPROGRAMS) *.o $(DEPSDIR)

format:
	clang-format -i $(wildcard *.c) $(wildcard $(INCLUDEDIR)/*.h)

.PHONY: all clean format
