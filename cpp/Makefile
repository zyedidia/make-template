PROGRAMS = main
all: $(PROGRAMS)

ALLPROGRAMS = $(PROGRAMS)

include rules.mk

%.o: %.cc $(BUILDSTAMP)
	$(CXX) $(CXXFLAGS) $(O) $(DEPCFLAGS) -o $@ -c $<

main: main.o
	$(CXX) $(CXXFLAGS) $(LDFLAGS) $(O) -o $@ $^

clean:
	rm -rf $(ALLPROGRAMS) *.o $(DEPSDIR)

.PHONY: all clean
