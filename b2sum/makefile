PROG=b2sum
PREFIX?=/usr/local
MANDIR?=$(PREFIX)/man
CC?=gcc
CFLAGS?=-O3 -march=native -static
CFLAGS+=-std=c99 -I../sse -fopenmp
LIBS=
#FILES=b2sum.c ../ref/blake2b-ref.c ../ref/blake2s-ref.c ../ref/blake2bp-ref.c ../ref/blake2sp-ref.c 
FILES=b2sum.c ../sse/blake2b.c ../sse/blake2s.c ../sse/blake2bp.c ../sse/blake2sp.c 
all: $(FILES)
	$(CC) $(FILES) $(CFLAGS) $(LIBS) -o $(PROG)

clean:
	rm -f $(PROG)

install:
	install -d $(DESTDIR)$(PREFIX)/bin
	install -d $(DESTDIR)$(MANDIR)/man1
	install -m 755 $(PROG) $(DESTDIR)$(PREFIX)/bin
	install -m 644 b2sum.1 $(DESTDIR)$(MANDIR)/man1/$(PROG).1
