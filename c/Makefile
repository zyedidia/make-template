PROGRAMS = main
all: $(PROGRAMS)

ALLPROGRAMS = $(PROGRAMS)

COMPILER = clang
include rules.mk

%.o: %.c $(BUILDSTAMP)
	$(CC) $(CFLAGS) $(O) $(DEPCFLAGS) -o $@ -c $<

main: main.o
	$(CC) $(CFLAGS) $(LDFLAGS) $(O) -o $@ $^

clean:
	rm -rf $(ALLPROGRAMS) *.o $(DEPSDIR)

.PHONY: all clean
