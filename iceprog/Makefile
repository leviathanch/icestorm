# CC = clang
LDLIBS = -lm
LDLIBS += $(shell pkg-config --libs libftdi)
LDLIBS += $(shell pkg-config --libs libftdi1)
CFLAGS = -MD -O0 -ggdb -Wall -std=c99
CFLAGS += $(shell pkg-config --libs libftdi)
CFLAGS += $(shell pkg-config --libs libftdi1)
DEST = $(DESTDIR)/usr

all: iceprog

iceprog: iceprog.o

install: all
	install -c iceprog $(DEST)/bin/iceprog

uninstall:
	rm -f $(DEST)/bin/iceprog

clean:
	rm -f iceprog
	rm -f *.o *.d

-include *.d

.PHONY: all install uninstall clean

