#The name of target.
TARGET = image

#The path of stoll target file.
TARGETDIR = $(shell pwd)/target

#The path of stoll the temporary object files.
export OBJSDIR = $(shell pwd)/objs

#The path of sub dir makefiles.
SUBMAKEFILES += controller/application
SUBMAKEFILES += controller/src
SUBMAKEFILES += sender/src
SUBMAKEFILES += receiver/src

#The path of global include files.
export GLOBALINCS = \
	$(shell pwd)/controller/include \
	$(shell pwd)/sender/include \
	$(shell pwd)/receiver/include

#The compiler.
export GXX = g++

#The flags of g++ compile.
export GXXFLAGS = -O2

#Start to compile.
$(TARGET):$(OBJSDIR) $(TARGETDIR)
#Run all of the makefile of sub dir.
	$(foreach temMake,$(SUBMAKEFILES),$(MAKE) -C $(temMake);)
#Compile the target.
	$(GXX) -o $(TARGETDIR)/$@ $(OBJSDIR)/*.o
#Finish compile, then remove the temporary files.
	$(RM) -r $(OBJSDIR)
	@echo "Compile seccussfully!"
	
#Make the dir of objs.
$(OBJSDIR):
	mkdir -p $@
	
#Make the dir of target.
$(TARGETDIR):
	mkdir -p $@
	
#The clran work.
clean:
	$(RM) -r $(TARGETDIR)
	
.PHONY:clean