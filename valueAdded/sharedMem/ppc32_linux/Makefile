#
# $Id: Makefile,v 1.3 2006/11/22 21:44:56 bernat Exp $
#

# Define any symbols needed to invoke configuration changes in make.config

# Include standard make configuration stuff that applies to everything
# in the paradyn tree.

NO_IMPLICIT_TEMPLATES = true

TO_CORE = ../../..

include $(TO_CORE)/make.config 

# Now make any necessary architecture specific changes to variables:
LD		= $(GXX)
LDFLAGS         += -shared

LDFLAGS_MUTATOR =  -L$(DEST) -ldyninstAPI

# The GNU headers for glibc conflict with RTposix.h
# CFLAGS		+= -D_SVID_SOURCE

# if we want to produce a shared object...
CFLAGS		+= -fPIC
CFLAGS          += -I. -I../..

VPATH        = ../src
#:../../dyninstAPI_RT/src

# Include the module-specific Makefile, which defines everything about
# the module that is common across architectures.

include ../make.module.tmpl

# Include the "standard program template".  This defines all the
# common targets like "clean", "install", etc.

include $(TO_CORE)/make.library.tmpl

