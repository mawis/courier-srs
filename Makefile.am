SUBDIRS = intl m4 po 

bin_PROGRAMS = courier-srs

noinst_HEADERS = courier-srs.h

courier-srs_SOURCES = courier-srs.cc

courier-srs_LDFLAGS = @LDFLAGS@

ACLOCAL_AMFLAGS = -I m4

EXTRA_DIST = config.rpath mkinstalldirs

DEFS = -DLOCALEDIR=\"$(localedir)\" @DEFS@
