# -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.
AC_PREREQ(2.59)
AC_INIT([libmspack],[0.3alpha],[kyzer@4u.net])
AC_CONFIG_MACRO_DIR([m4])
AM_INIT_AUTOMAKE
AM_MAINTAINER_MODE
AC_CONFIG_SRCDIR([mspack/mspack.h])
AC_CONFIG_HEADER([config.h])
AC_CANONICAL_HOST

# --enable-debug option
AC_ARG_ENABLE(debug,
  AS_HELP_STRING(--enable-debug,enable debugging),
  enable_debug=$enableval,
  enable_debug=no)
if test x$enable_debug = xyes; then
  AC_DEFINE(DEBUG, 1, [Turn debugging mode on?])
fi
AM_CONDITIONAL(DEBUG, test x$enable_debug = 'xyes')

# Checks for programs.
AC_PROG_CXX
AC_PROG_AWK
AC_PROG_CC
AM_PROG_CC_C_O
AC_PROG_CPP
AC_PROG_INSTALL
AC_PROG_LN_S
AC_PROG_MAKE_SET
AC_PROG_RANLIB
LT_INIT
AC_EXEEXT
PKG_PROG_PKG_CONFIG

# Checks for header files.
AC_HEADER_STDC
AC_CHECK_HEADERS([ctype.h limits.h stdlib.h wctype.h])

# Checks for typedefs, structures, and compiler characteristics.
AC_C_CONST
AC_C_INLINE
AC_TYPE_MODE_T
AC_TYPE_OFF_T
AC_TYPE_SIZE_T
AC_TYPE_UINT32_T
AC_CHECK_SIZEOF([off_t])
AC_CHECK_FUNCS([tolower towlower])

# largefile support
AC_SYS_LARGEFILE
AC_FUNC_FSEEKO

# Checks for library functions.
AC_FUNC_MALLOC
AC_CHECK_FUNCS([memset mkdir strcasecmp strrchr])

AC_CONFIG_FILES([Makefile doc/Makefile doc/Doxyfile libmspack.pc])
AC_OUTPUT
