SHELL = /bin/sh
NAME = all
MAKEFILE = Makefile

# Include machine specific flags and locations (inc. files & libs)
#
#include $(RATROOT)/src/make/Make.include

##BONSAI_LIBS  = $(shell $(GENIE)/src/scripts/setup/genie-config --libs)
RAT_LIBS = -L$(RATROOT)/lib -lRATEvent -lrat -L$(ROOTSYS)/lib -lCore -lRIO -lTree -lPhysics -lMathCore
ROOT_FLAG = `root-config --cflags --libs`


LIBRARIES  := $(LIBRARIES) $(CERN_LIBRARIES) $(RAT_LIBS)

INCLUDES := $(INCLUDES) -I$(RATROOT)/include -I$(RATROOT)/src/fit/bonsai -I$(ROOTSYS)/include

all: visualizer

visualizer: FORCE
	$(CXX) -g $(ROOT_FLAG) -o  visualizer $(CXXFLAGS) $(LDFLAGS) visualizer.cc $(INCLUDES) $(LIBRARIES)

#################### CLEANING

purge: FORCE
	$(RM) *.o *~ core 

clean: FORCE
	$(RM) *.o *~ core 
	$(RM) visualizer

dumb: FORCE
	g++ `root-config --cflags --libs` -g -o visualizer visualizer.cc  -I/data/kneale/ratpac/rat-pac/include   -L/data/kneale/ratpac/rat-pac/lib -lRATEvent -lrat -I/data/kneale/ratpac/rat-pac/src/fit/bonsai/
FORCE:

# DO NOT DELETE
