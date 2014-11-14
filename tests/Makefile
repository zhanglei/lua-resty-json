SRC := unit_test.cxx
OBJ := ${SRC:.cxx=.o}

CXXFLAGS := -Wall -O0 -g -MMD
LDFLAGS := -Wl,-rpath=.. -L.. -lljson

PROGRAM = unit_test

.PHONY = all test

all : $(PROGRAM)

$(PROGRAM) : $(OBJ) ../libljson.so
	$(CXX) $(OBJ) $(LDFLAGS) -o $@
	@-cat *.d > dep.txt

${OBJ} : %.o : %.cxx
	$(CXX) $(CXXFLAGS) -c $<

-include dep.txt

clean:
	rm -f *.txt *.d *.o $(PROGRAM)