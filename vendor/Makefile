LCI       := lci-0.10.5
NPIET     := npiet-1.3c
CFUNGE    := cfunge-0.9.0
ACME_CHEF := Acme-Chef-1.01
LOCAL     := $(CURDIR)/local

all: $(LOCAL)/bin/lci $(LOCAL)/bin/npiet $(LOCAL)/bin/cfunge $(LOCAL)/bin/compilechef

$(LOCAL)/bin/lci:
	unzip $(LCI).zip
	(cd $(LCI) && cmake -DCMAKE_INSTALL_PREFIX=$(LOCAL) . && make && make install)

$(LOCAL)/bin/npiet:
	mkdir -p $(LOCAL)/man/man1 $(LOCAL)/man/man3 # workaround
	tar xzf $(NPIET).tar.gz
	(cd $(NPIET) && ./configure --prefix=$(LOCAL) && make && make install)

$(LOCAL)/bin/cfunge:
	tar xjf $(CFUNGE).tar.bz2
	(cd $(CFUNGE) && cmake -DCMAKE_INSTALL_PREFIX=$(LOCAL) . && make && make install)

$(LOCAL)/bin/compilechef:
	tar xzf $(ACME_CHEF).tar.gz
	(cd $(ACME_CHEF) && perl Makefile.PL INSTALL_BASE=$(LOCAL) && make && make install)

clean:
	rm -rf $(LOCAL)/ $(LCI)/ $(NPIET)/ $(CFUNGE)/ $(ACME_CHEF)
