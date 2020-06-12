MAINTAINERCLEANFILES = $(srcdir)/Makefile.in

if ENABLE_CTAPI
bin_PROGRAMS = key-generator

lib_LTLIBRARIES = libcardservice.la
include_HEADERS = sc-hsm-cardservice.h

#libcardservice_la_LIBADD = $(top_builddir)/src/ctccid/libctccid.la
libcardservice_la_SOURCES = sc-hsm-cardservice.c

libcardservice_la_LDFLAGS = $(AM_LDFLAGS) \
			    $(top_builddir)/src/common/libcommon.la \
		            -export-symbols "$(srcdir)/libcardservice.exports" \
	                    -module -shared -avoid-version -no-undefined -pthread

AM_CPPFLAGS = -I$(top_srcdir)/src

key_generator_SOURCES = key-generator.c

key_generator_LDADD = $(top_builddir)/src/ctccid/libctccid.la \
		      libcardservice.la
endif
