PROG = main
all: $(PROG)

include rules.mk

INCDIR = include
INC = $(INCDIR)
INC_PARAMS=$(foreach d, $(INC), -I$d)
CXXFLAGS += $(INC_PARAMS)

SRC = $(wildcard *.cc)
OBJ = $(SRC:.cc=.o)

%.o: %.cc $(BUILDSTAMP)
	$(CXX) $(CXXFLAGS) $(O) $(DEPCFLAGS) -o $@ -c $<

$(PROG): $(OBJ)
	$(CXX) $(CXXFLAGS) $(LDFLAGS) $(O) -o $@ $^

# for inspecting assembly
%.s: %.cc $(BUILDSTAMP)
	$(CXX) $(CXXFLAGS) $(O) $(DEPCFLAGS) -o $@ -S $<

clean:
	rm -rf $(ALLPROGRAMS) *.o *.s $(DEPSDIR)

format:
	clang-format -i $(SRC) $(wildcard $(INCDIR)/*.hh)

.PHONY: all clean format
