PROGNAME = tiv

OBJECTS = tiv.o

CXX      ?= g++
CXXFLAGS ?= -O2 -fpermissive
INSTALL  ?= install
INSTALL_PROGRAM ?= $(INSTALL) -D

# https://www.gnu.org/prep/standards/html_node/Directory-Variables.html#Directory-Variables
prefix      ?= /usr/local
exec_prefix ?= $(prefix)
bindir      ?= $(exec_prefix)/bin

override CXXFLAGS += -Wall -fexceptions
override LDFLAGS  += -pthread
#override LDLIBS   += -static

all: $(PROGNAME)

tiv.o: CImg.h

$(PROGNAME): $(OBJECTS)
	$(CXX) $(LDFLAGS) $^ -o $@ $(LOADLIBES) $(LDLIBS)

install: all
	$(INSTALL_PROGRAM) $(PROGNAME) $(DESTDIR)$(bindir)/$(PROGNAME)

clean:
	$(RM) -f $(PROGNAME) *.o

.PHONY: all install clean
