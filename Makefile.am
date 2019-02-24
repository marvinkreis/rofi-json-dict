ACLOCAL_AMFLAGS=-I m4
plugindir=@rofi_PLUGIN_INSTALL_DIR@

plugin_LTLIBRARIES = jsondict.la

jsondict_la_SOURCES=\
		 src/jsondict.c

jsondict_la_CFLAGS= @glib_CFLAGS@ @rofi_CFLAGS@ @jsonc_CFLAGS@
jsondict_la_LIBADD= @glib_LIBS@ @rofi_LIBS@ @jsonc_LIBS@
jsondict_la_LDFLAGS= -module -avoid-version
