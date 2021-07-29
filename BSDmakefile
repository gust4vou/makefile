#
# Universidade Federal do Rio de Janeiro
# Escola Politecnica
# Departamento de Eletronica e de Computacao
# EEL270 = Computacao II - Turma 2021/1
# Prof. Marcelo Luiz Drumond Lanza
# Autor:
# Descricao:
#
# $Author$
# $Date$
# $Log$

OS = `uname -s`

CC = gcc

.ifdef CLANG
CC = clang
.endif

LD = $(CC)

DIALETO = ansi
STANDARD = -ansi

.ifndef C89
DIALETO = c89
STANDARD = -std=c89
.elif C99
DIALETO = c99
STANDARD = -std=c99
.elif C11
DIALETO = c11
STANDARD = -std=c11
.endif

DEBUG =

.ifdef DEPURACAO
DEBUG = -DDEPURACAO
.endif

CFLAGS = -Wall -std=$(STANDARD) $(DEBUG)
LFLAGS = -Wall

AULA01 = aula0101
AULA0101OBJS = aula0101.o

EXECS = aula0101

LIBS =

ALL = $(EXECS) $(LIBS)

.c.o:
    $(CC) $(CFLAGS) -c $<

all: $(ALL)

aula01:

aula0101: $(AULA0101OBJS)
    $(LD) $(LFLAGS) -o $@ $(AULA0101OBJS)
    cp -f $@ $@-$(OS)-$(CC)-$(DIALETO)

.PHONY: clean-all\
        clean\
        clean-objs\
        clean-bsd\
        clean-linux\
        clean-gcc\
        clean-clang\
        clean-ansi\
        clean-c89\
        clean-c99\
        clean-c11

clean:
    rm -f *.o $(ALL) *.core

clean-all:
    rm -f *.o $(ALL) *-FreeBSD-* *-Linux-* *.core

clean-freebsd:
	rm -f *.o $(ALL) *-FreeBSD-* *.core

clean-linux:
	rm -f *.o $(ALL) *-Linux-* *.core

clean-gcc:
    rm -f *.o $(ALL) *-gcc-* *.core

clean-clang:
    rm -f *.o $(ALL) *-clang-* *.core

clean-ansi:
    rm -f *.o $(ALL) *-ansi-* *.core

clean-c89:
    rm -f *.o $(ALL) *-c89-* *.core

clean-c99:
    rm -f *.o $(ALL) *-c99-* *.core

clean-c11:
    rm -f *.o $(ALL) *-c11-* *.core

clean-objs:
	rm -f *.o *.core

# $RCSfile$