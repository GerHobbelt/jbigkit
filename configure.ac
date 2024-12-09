#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ([2.69])
AC_INIT([jbigkit], [2.22], [pullmoll@t-online.de])
AM_INIT_AUTOMAKE(subdir-objects)

AC_CONFIG_SRCDIR([libjbig/jbig.h])
AC_CONFIG_HEADERS([config.h])
AC_CONFIG_MACRO_DIR([m4])

JBIG_LT_CURRENT=2
JBIG_LT_REVISION=22
JBIG_LT_AGE=0

AC_SUBST(JBIG_LT_CURRENT)
AC_SUBST(JBIG_LT_REVISION)
AC_SUBST(JBIG_LT_AGE)

JBIG85_LT_CURRENT=2
JBIG85_LT_REVISION=22
JBIG85_LT_AGE=0

AC_SUBST(JBIG85_LT_CURRENT)
AC_SUBST(JBIG85_LT_REVISION)
AC_SUBST(JBIG85_LT_AGE)

AM_INIT_AUTOMAKE

# Checks for programs.
AC_PROG_CC
AM_PROG_CC_C_O
AC_PROG_MAKE_SET
LT_INIT

# Package check
AC_ARG_ENABLE([tests],
	AS_HELP_STRING([--enable-tests], [Enable codec tests]))

AS_IF([test "x$enable_tests" = "xyes"], [PKG_CHECK_MODULES([CHECK], [check >= 0.9.19])])

# Checks for libraries.
AC_CHECK_LIB([jbig], [jbg_enc_init])
AC_CHECK_LIB([jbig85], [jbg85_enc_init])

# Checks for header files.
AC_CHECK_HEADERS([limits.h stddef.h stdlib.h string.h])

# Checks for typedefs, structures, and compiler characteristics.
AC_TYPE_SIZE_T
AC_CHECK_TYPES([ptrdiff_t])

# Checks for library functions.
AC_FUNC_MALLOC
AC_FUNC_REALLOC
AC_CHECK_FUNCS([memchr memset])

AC_CONFIG_FILES([Makefile libjbig/Makefile pbmtools/Makefile test/Makefile
	jbigkit.pc jbigkit85.pc])
AC_OUTPUT
