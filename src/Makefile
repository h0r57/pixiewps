CCFLAGS ?= -std=c99 -O3

TARGET = pixiewps
CRYPTO = crypto/sha256.c crypto/md.c crypto/md_wrap.c
SOURCE = $(TARGET).c random_r.c $(CRYPTO)
LIBS   = -lpthread

PREFIX ?= $(DESTDIR)/usr
BINDIR = $(PREFIX)/bin

all:
	$(CC) $(CFLAGS) $(CCFLAGS) $(CPPFLAGS) -o $(TARGET) $(SOURCE) $(LIBS) $(LDFLAGS)

debug:
	$(CC) $(CLFAGS) $(CCFLAGS) $(CPPFLAGS) -DDEBUG -o $(TARGET) $(SOURCE) $(LIBS) $(LDFLAGS)

install:
	rm -f $(BINDIR)/$(TARGET)
	install -d $(BINDIR)
	install -m 755 $(TARGET) $(BINDIR)

uninstall:
	rm -f $(BINDIR)/$(TARGET)

clean:
	rm -f $(TARGET)
