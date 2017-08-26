#The makefile of sub dir.
#Auther: Tianz
#Copyright: ElegantRobot, 22 Aug 2017

#The source files.
SRC = $(wildcard *.cpp)

#The object files.
OBJS = $(SRC:%.cpp=%.o)

#Compile the objects.
all:$(OBJS)
	
$(OBJS):%.o:%.cpp
	$(GXX) -o $(OBJSDIR)/$@ -c $< $(GLOBALINCS) $(GXXFLAGS)