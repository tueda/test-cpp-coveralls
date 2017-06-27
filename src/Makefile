CC       = gcc
CFLAGS   = -g -O0 -coverage -Wall -Wextra -std=c99 -pedantic
CXX      = g++
CPPFLAGS =
DEFS     =
LDFLAGS  =
DEPDIR   = .deps

CCLINK   = $(CC)  $(CFLAGS)   $(LDFLAGS)

BIN1  = test1
OBJ1  = test1.o
LIB1  =
LINK1 = $(CCLINK)

BIN = $(BIN1) $(BIN2) $(BIN3) $(BIN4) $(BIN5) $(BIN6) $(BIN7) $(BIN8) $(BIN9)
OBJ = $(OBJ1) $(OBJ2) $(OBJ3) $(OBJ4) $(OBJ5) $(OBJ6) $(OBJ7) $(OBJ8) $(OBJ9)

all: $(BIN)

$(BIN1): $(OBJ1)
	$(LINK1) -o $(BIN1) $(OBJ1) $(LIB1)

mostlyclean:
	rm -rf $(OBJ)

clean:
	rm -rf $(BIN) $(OBJ) $(DEPDIR) *.gcda *.gcno

.SUFFIXES: .o .c

.c.o:
	$(CC) $(DEFS) $(CPPFLAGS) $(CFLAGS) -c -MD -o $@ $< && { [ -d $(DEPDIR) ] || mkdir $(DEPDIR); } && mv $*.d $(DEPDIR)

-include $(DEPDIR)/*.d
