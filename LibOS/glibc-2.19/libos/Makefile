# Copyright (C) 1996-2001,2002,2003,2004,2005,2006
#	Free Software Foundation, Inc.
# This file is part of the GNU C Library.

# The GNU C Library is free software; you can redistribute it and/or
# modify it under the terms of the GNU Lesser General Public
# License as published by the Free Software Foundation; either
# version 2.1 of the License, or (at your option) any later version.

# The GNU C Library is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU
# Lesser General Public License for more details.

# You should have received a copy of the GNU Lesser General Public
# License along with the GNU C Library; if not, write to the Free
# Software Foundation, Inc., 59 Temple Place, Suite 330, Boston, MA
# 02111-1307 USA.

# Makefile for the libos library.

subdir		:= libos

# Installed header files.
headers		:= 

# Internal header files.
distribute	:= errno.h

liblibos-routines := checkpoint sandbox msgpersist benchmark

# Build the -llibos library.

extra-libs	:= liblibos
extra-libs-others = $(extra-libs)

include ../Makeconfig

ifeq ($(versioning),yes)
liblibos-routines	+=
liblibos-shared-only-routines :=
endif

tests =

modules-names =

extra-test-objs += $(modules-names:=.os)
generated := $(modules-names:=.so)

include ../Rules

# Depend on libc.so so a DT_NEEDED is generated in the shared objects.
# This ensures they will load libc.so for needed symbols if loaded by
# a statically-linked program that hasn't already loaded it.
$(objpfx)liblibos.so: $(common-objpfx)libc.so $(common-objpfx)libc_nonshared.a
