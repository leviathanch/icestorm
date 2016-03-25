# CXX = clang
CXX ?= clang
LDLIBS = -lm -lstdc++
CXXFLAGS = -MD -O0 -ggdb -Wall -std=c++11
CC = $(CXX)
DEST = $(DESTDIR)/usr

all: icemulti

icemulti: icemulti.o

install: all
	install -c icemulti $(DEST)/bin/icemulti

uninstall:
	rm -f $(DEST)/bin/icemulti

clean:
	rm -f icemulti
	rm -f *.o *.d

-include *.d

.PHONY: all install uninstall clean

