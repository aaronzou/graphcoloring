CPLEX_LIB       = /opt/ibm/ILOG/CPLEX_Studio126/cplex/lib/x86-64_linux/static_pic/libcplex.a /opt/ibm/ILOG/CPLEX_Studio126/cplex/lib/x86-64_linux/static_pic/libilocplex.a
LP_LIBS         = $(CPLEX_LIB)
INC_DIR		= -I/opt/ibm/ILOG/CPLEX_Studio126/cplex/include/ -I/opt/ibm/ILOG/CPLEX_Studio126/concert/include/

CCC = g++

CCFLAGS = -std=c++11 -m64 -O2 -fPIC -fexceptions -DNDEBUG -DIL_STD

LDFLAGS = $(LP_LIBS) -lc -lm

SRCPRI = coloring.cpp 

SOURCES = $(SRCPRI)

OBJECTS = $(SOURCES:.cpp=.o)

EXECUTABLE = coloring

all: $(OBJECTS) 
	$(CCC) -o coloring $(OBJECTS) $(CCFLAGS) $(LDFLAGS) -lpthread -lm -lnsl
	cp -f coloring ../exp

clean:
	rm -rf $(EXECUTABLE) $(OBJECTS)

#
# produce the .o files from the .cc and .c files
#

%.o: %.cpp
	$(CCC) $(CCFLAGS) $(INC_DIR) -c $<