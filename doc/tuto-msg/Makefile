# This Makefile is specifically tailored for the binaries of this tutorial.

# For your own project, you should use the one provided at 
# http://simgrid.gforge.inria.fr/simgrid/latest/doc/install_yours.html

# Some configuration
SIMGRID_INSTALL_PATH ?= ../.. # Where you installed simgrid 
CC ?= gcc                     # Your compiler (on Mac, use clang instead)

# No change needed bellow for this tutorial.
############################################################################

all: masterworker

WARNING = -Wshadow -Wcast-align -Waggregate-return -Wmissing-prototypes \
          -Wmissing-declarations -Wstrict-prototypes -Wmissing-prototypes \
          -Wmissing-declarations -Wmissing-noreturn -Wredundant-decls \
	  -Wnested-externs -Wpointer-arith -Wwrite-strings
WARNING += -Werror # Comment that line to not be in paranoid mode

# CFLAGS = -std=gnu99 -g -O0 $(WARNINGS) $(EXTRA_CFLAGS) # Use this line to make debugging easier
CFLAGS = -std=gnu99 -g -O2 $(WARNINGS) $(EXTRA_CFLAGS) # Use this line to get better performance

# No change should be mandated past that line
#############################################
# The following are implicit rules, used by default to actually build
# the targets for which you listed the dependencies above.

# The blanks before the $(CC) must be a Tab char, not spaces
%: %.c
	$(CC) -I$(strip $(SIMGRID_INSTALL_PATH))/include -L$(strip $(SIMGRID_INSTALL_PATH))/lib/  $(CFLAGS) $^ -lsimgrid -o $@ 

clean:
	rm -f *.o *~ masterworker masterworker-sol1 masterworker-sol2 masterworker-sol3 masterworker-sol4
.PHONY: clean
