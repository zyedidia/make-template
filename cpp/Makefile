PROGRAMS = main
all: $(PROGRAMS)

ALLPROGRAMS = $(PROGRAMS)

include rules.mk

INCLUDEDIR = include
INCLUDES = $(INCLUDEDIR)
CXXFLAGS += -I$(INCLUDES)

%.o: %.cc $(BUILDSTAMP)
	$(CXX) $(CXXFLAGS) $(O) $(DEPCFLAGS) -o $@ -c $<

main: main.o
	$(CXX) $(CXXFLAGS) $(LDFLAGS) $(O) -o $@ $^

clean:
	rm -rf $(ALLPROGRAMS) *.o $(DEPSDIR)

format:
	clang-format -i $(wildcard *.cc) $(wildcard $(INCLUDEDIR)/*.hh)

.PHONY: all clean format
