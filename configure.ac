#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_INIT([libpostal], [0.1])
AM_INIT_AUTOMAKE([foreign subdir-objects])
AC_CONFIG_SRCDIR([src])
LT_INIT([shared])

AC_CONFIG_HEADERS([config.h])

# Checks for programs.
AC_PROG_CC_C99
AC_PROG_INSTALL

# Checks for libraries.
AC_SEARCH_LIBS([snappy_compress],
  [snappy],,[AC_MSG_ERROR([Could not find snappy])
])
AC_SEARCH_LIBS([log],
  [m],,[AC_MSG_ERROR([Could not find math library])])

# Checks for header files.
AC_HEADER_STDC
AC_HEADER_TIME
AC_HEADER_DIRENT
AC_CHECK_HEADERS([fcntl.h float.h inttypes.h limits.h locale.h malloc.h memory.h stddef.h stdint.h stdlib.h string.h unistd.h])

# Checks for typedefs, structures, and compiler characteristics.
AC_CHECK_HEADER_STDBOOL
AC_C_INLINE
AC_TYPE_INT16_T
AC_TYPE_INT32_T
AC_TYPE_INT64_T
AC_TYPE_INT8_T
AC_TYPE_OFF_T
AC_TYPE_SIZE_T
AC_TYPE_SSIZE_T
AC_TYPE_UINT16_T
AC_TYPE_UINT32_T
AC_TYPE_UINT64_T
AC_TYPE_UINT8_T
AC_CHECK_TYPES([ptrdiff_t])

# Checks for library functions.
AC_FUNC_MALLOC
AC_FUNC_MMAP
AC_FUNC_REALLOC
AC_CHECK_FUNCS([getcwd gettimeofday memmove memset munmap regcomp setlocale sqrt strdup strndup])

AC_CONFIG_FILES([Makefile
                 src/Makefile
                 src/sparkey/Makefile])

AC_CHECK_PROG([FOUND_SHUF], [shuf], [yes])
AC_CHECK_PROG([FOUND_GSHUF], [gshuf], [yes])

AS_IF([test "x$FOUND_SHUF" = xyes],  [AC_DEFINE([HAVE_SHUF], [1], [shuf available])])
AS_IF([test "x$FOUND_GSHUF" = xyes],  [AC_DEFINE([HAVE_GSHUF], [1], [gshuf available])])

LIBPOSTAL_DATA_DIR=$datadir/libpostal
AC_DEFINE_UNQUOTED([LIBPOSTAL_DATA_DIR], ["$LIBPOSTAL_DATA_DIR"], [Data directory for libpostsal])
AC_SUBST(LIBPOSTAL_DATA_DIR)


AC_OUTPUT
