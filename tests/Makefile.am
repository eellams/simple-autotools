
TESTS = check_something

LIBSOMETHING = $(top_builddir)/src/libsomething.la

check_PROGRAMS = $(TESTS)

check_something_SOURCES = check_something.c
check_something_CFLAGS = @CHECK_CFLAGS@ -DCHECK
check_something_LDADD = $(LIBSOMETHING) @CHECK_LIBS@

