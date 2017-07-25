TARGET = my_app.out
# List C source files here. (C dependencies are automatically generated.)
SRC = hellomake.c hellofunc.c

CC=gcc
IDIR =../inc
CFLAGS=-I$(IDIR)

ODIR=obj
# LDIR =../lib
# LIBS=-lm

_DEPS = hellomake.h
DEPS = $(addprefix $(IDIR)/,$(_DEPS))

# _OBJ = hellomake.o hellofunc.o 
# OBJ = $(addprefix $(ODIR)/,$(_OBJ))
OBJ = $(addprefix $(ODIR)/,$(SRC:.c=.o))

REMOVE = rm -f

# we define a rule that applies to all files ending in the .o suffix
# o is dependent to h files, so if h changes compile again
# -c: just compile obj, do not link
$(ODIR)/%.o: %.c $(DEPS)
	$(CC) -c -o $@ $< $(CFLAGS)

# just check object files, if not changed, do not compile
all: $(OBJ)
	$(CC) -o $(TARGET) $^ $(CFLAGS)
	# $(CC) -o $@ $^ $(CFLAGS) $(LIBS)


clean:
	$(REMOVE) $(OBJ)
	$(REMOVE) $(TARGET)

debug:
	@echo $(OBJ)
	@echo $(OBJ2)
	# @echo $(DEPT)

.PHONY : all clean debug
