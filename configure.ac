dnl# -*- Autoconf -*-
dnl# Process this file with autoconf to produce a configure script.
AC_PREREQ([2.69.185-b502e])
AC_INIT([libmspack],[0.3alpha],[kyzer@4u.net])
AC_CONFIG_AUX_DIR([build-aux])
AC_CONFIG_MACRO_DIR([m4])
AM_INIT_AUTOMAKE([foreign subdir-objects])
AM_MAINTAINER_MODE
AC_CONFIG_SRCDIR([mspack/mspack.h])
AC_CONFIG_HEADERS([config.h])
AC_CANONICAL_HOST

# --enable-debug option
AC_ARG_ENABLE([debug],
  [AS_HELP_STRING([--enable-debug],[enable debugging])],
  [enable_debug=${enableval}],
  [enable_debug=no])
if test "x${enable_debug}" = "xyes"; then
  AC_DEFINE([DEBUG],[1],[Turn debugging mode on?])
fi
AM_CONDITIONAL([DEBUG],[test x${enable_debug} = 'xyes'])dnl

# Checks for programs.
AM_PROG_AR
if test "x${AR}" = "x"; then
  test -z "${AR}" || unset AR
  AC_CHECK_TOOLS([AR],[ar gar])dnl
  ## might want to switch around these checks...
  if test "x${ac_cv_prog_AR}" = "x"; then
    test -z "${ac_cv_prog_AR}" || unset ac_cv_prog_AR
    m4_ifdef([AC_PROG_AR],[
      AC_PROG_AR
    ],[
      test -x "`which ar`" && echo "first ar in path is `which ar`"
    ])
  fi
else
  test -n "${AR}" && export AR
fi
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
# Autoupdate added the following line to ensure that your configure
# script's behavior did not change.  It is probably safe to remove.
AC_CHECK_INCLUDES_DEFAULT
AC_CHECK_HEADERS([ctype.h limits.h stdlib.h wctype.h])dnl

if test "x${ac_cv_header_stdint_h}" = "x"; then
  test -z "${ac_cv_header_stdint_h}"
  AC_CHECK_HEADERS([stdint.h])
fi
if test "x${ac_cv_header_strings_h}" = "x"; then
  test -z "${ac_cv_header_strings_h}"
  AC_CHECK_HEADERS([strings.h])
fi
if test "x${ac_cv_header_unistd_h}" = "x"; then
  test -z "${ac_cv_header_unistd_h}"
  AC_CHECK_HEADERS([unistd.h])
fi

# Checks for typedefs, structures, and compiler characteristics.
AC_C_CONST
AC_C_INLINE
AC_TYPE_MODE_T
AC_TYPE_OFF_T
AC_TYPE_SIZE_T
AC_TYPE_UINT32_T
AC_CHECK_SIZEOF([off_t])
AC_CHECK_FUNCS([tolower towlower])dnl

# largefile support
AC_SYS_LARGEFILE
AC_FUNC_FSEEKO

# Checks for library functions.
AC_FUNC_MALLOC
AC_CHECK_FUNCS([memset mkdir strcasecmp strrchr])dnl

# Output.
AC_CONFIG_FILES([Makefile doc/Makefile doc/Doxyfile libmspack.pc])
AC_OUTPUT
