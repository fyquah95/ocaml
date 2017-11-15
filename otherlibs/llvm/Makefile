#**************************************************************************
#*                                                                        *
#*                                 OCaml                                  *
#*                                                                        *
#*            Xavier Leroy, projet Cristal, INRIA Rocquencourt            *
#*                                                                        *
#*   Copyright 1999 Institut National de Recherche en Informatique et     *
#*     en Automatique.                                                    *
#*                                                                        *
#*   All rights reserved.  This file is distributed under the terms of    *
#*   the GNU Lesser General Public License version 2.1, with the          *
#*   special exception on linking described in the file LICENSE.          *
#*                                                                        *
#**************************************************************************

# Makefile for llvm backend library

LIBNAME=llvm

EXTRACAMLFLAGS=-nolabels -w -32-34-37-50-60

LDOPTS=$(NATIVECCLIBS)

COBJS=executionengine_ocaml.o vectorize_ocaml.o transform_utils_ocaml.o \
      llvm_ocaml.o irreader_ocaml.o scalar_opts_ocaml.o bitwriter_ocaml.o \
      analysis_ocaml.o passmgr_builder_ocaml.o bitreader_ocaml.o \
      ipo_ocaml.o linker_ocaml.o all_backends_ocaml.o \
      target_ocaml.o

CAMLOBJS=llvm_linker.cmo llvm_bitreader.cmo llvm_scalar_opts.cmo \
  llvm_passmgr_builder.cmo llvm_all_backends.cmo llvm_vectorize.cmo \
  llvm_target.cmo llvm_transform_utils.cmo llvm_analysis.cmo llvm_ipo.cmo \
  llvm_irreader.cmo llvm.cmo

include ../Makefile

.PHONY: depend
depend:
	$(CC) -MM $(CPPFLAGS) *.c >.depend
	$(CAMLRUN) ../../tools/ocamldep -slash *.mli *.ml >> .depend

include .depend
