SHELL = /bin/sh
.SUFFIXES:
.SUFFIXES: .c .o

CC = gcc

CFLAGS = -fPIC -Wall -g -O0 -D_GNU_SOURCE

INCLUDES = -I./src -I/usr/include/glib-2.0/ -I/usr/lib/x86_64-linux-gnu/glib-2.0/include/ 

LFLAGS = -L/usr/lib -lglib-2.0 `pkg-config --cflags --libs gio-2.0`

INSTALL = /usr/bin/install

INSTALL_PROGRAM = $(INSTALL)

INSTALL_DATA = ${INSTALL} -m 644

SRCS = client.c

OBJS = $(SRCS:.c=.o)

TARGET = rfsubmgr

INSTALL_DIR = bin

PREFIX = $(DESTDIR)/usr

BINDIR = $(PREFIX)/bin

CONFDIR = $(DESTDIR)/etc/redfish_event_listener

MANDIR = $(DESTDIR)/usr/share/man/man1

all:
	$(CC) $(CFLAGS) $(INCLUDES) $(INCLUDES_IQUOTE) -o $(TARGET) $(SRCS) $(LFLAGS)

clean:
	$(RM) $(TARGET) src/*/*.o *.deb
