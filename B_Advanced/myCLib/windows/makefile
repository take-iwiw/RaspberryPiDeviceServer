include ../makefile_config

TARGET = ../MyDeviceDrivers.dll
SRCS = deviceDrivers.cpp
INCLUDES = -I../
SUBS =
SUBDIRS =

all: sub_target $(TARGET)

$(TARGET): $(OBJS) $(SUBS)
	$(CC) $(LDFLAGS) -shared -o $@ $(OBJS) $(SUBS) 

.PHONY: sub_target
sub_target:
ifdef SUBDIRS
	$(foreach subdir,$(SUBDIRS),cd $(subdir) && $(MAKE) && cd ../ &&) cd ./
endif

.PHONY: clean
clean:
	$(DEL) *.o *.a *.exe *.dll
ifdef SUBDIRS
	$(foreach subdir,$(SUBDIRS),cd $(subdir) && $(MAKE) clean && cd ../ &&) cd ./
endif

