# CXX = clang
CXX ?= clang
LDLIBS = -lm -lstdc++
CXXFLAGS = -MD -O0 -ggdb -Wall -std=c++11
CC = $(CXX)
DEST = $(DESTDIR)/usr

all: icepack iceunpack

icepack: icepack.o

iceunpack: icepack
	ln -sf icepack iceunpack

install: all
	install -c icepack $(DEST)/bin/icepack
	ln -sf icepack $(DEST)/bin/iceunpack

uninstall:
	rm -f $(DEST)/bin/icepack
	rm -f $(DEST)/bin/iceunpack

clean:
	rm -f icepack
	rm -f iceunpack
	rm -f *.o *.d

-include *.d

.PHONY: all install uninstall clean

