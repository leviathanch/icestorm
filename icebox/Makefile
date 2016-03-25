DEST = $(DESTDIR)/usr
INSTALL = /usr/bin/install -c

all: chipdb-1k.txt chipdb-8k.txt

chipdb-1k.txt: icebox.py iceboxdb.py icebox_chipdb.py
	python3 icebox_chipdb.py > chipdb-1k.new
	mv chipdb-1k.new chipdb-1k.txt

chipdb-8k.txt: icebox.py iceboxdb.py icebox_chipdb.py
	python3 icebox_chipdb.py -8 > chipdb-8k.new
	mv chipdb-8k.new chipdb-8k.txt

clean:
	rm -f chipdb-1k.txt chipdb-8k.txt
	rm -f icebox.pyc iceboxdb.pyc

install: all
	$(INSTALL) chipdb-1k.txt     $(DEST)/share/icebox/
	$(INSTALL) chipdb-8k.txt     $(DEST)/share/icebox/
	$(INSTALL) icebox.py         $(DEST)/bin/icebox.py
	$(INSTALL) iceboxdb.py       $(DEST)/bin/iceboxdb.py
	$(INSTALL) icebox_chipdb.py  $(DEST)/bin/icebox_chipdb
	$(INSTALL) icebox_diff.py    $(DEST)/bin/icebox_diff
	$(INSTALL) icebox_explain.py $(DEST)/bin/icebox_explain
	$(INSTALL) icebox_colbuf.py  $(DEST)/bin/icebox_colbuf
	$(INSTALL) icebox_html.py    $(DEST)/bin/icebox_html
	$(INSTALL) icebox_maps.py    $(DEST)/bin/icebox_maps
	$(INSTALL) icebox_vlog.py    $(DEST)/bin/icebox_vlog

uninstall:
	rm -f $(DEST)/bin/icebox.py
	rm -f $(DEST)/bin/iceboxdb.py
	rm -f $(DEST)/bin/icebox_chipdb
	rm -f $(DEST)/bin/icebox_diff
	rm -f $(DEST)/bin/icebox_explain
	rm -f $(DEST)/bin/icebox_colbuf
	rm -f $(DEST)/bin/icebox_html
	rm -f $(DEST)/bin/icebox_maps
	rm -f $(DEST)/bin/icebox_vlog
	rm -f $(DEST)/share/icebox/chipdb-1k.txt
	rm -f $(DEST)/share/icebox/chipdb-8k.txt
	-rmdir $(DEST)/share/icebox

.PHONY: all clean install uninstall

