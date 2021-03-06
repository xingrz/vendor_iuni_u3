#                                               -*- Autoconf -*-

# configure.ac -- Autoconf script for QMI Framework
#

# Process this file with autoconf to produce a configure script

# Requires autoconf tool later than 2.61
AC_PREREQ(2.61)
# Initialize the qmi-framework package version 1.0.0
AC_INIT([qmi-framework],1.0.0)
# Does not strictly follow GNU Coding standards
AM_INIT_AUTOMAKE([foreign])
# Disables auto rebuilding of configure, Makefile.ins
AM_MAINTAINER_MODE
# Verifies the --srcdir is correct by checking for the path
AC_CONFIG_SRCDIR([qcci/src/qmi_cci_common.c])
# defines some macros variable to be included by source
AC_CONFIG_HEADERS([config.h])
AC_CONFIG_MACRO_DIR([m4])

# Checks for programs.
AC_PROG_CC
AM_PROG_CC_C_O
AC_PROG_LIBTOOL
AC_PROG_AWK
AC_PROG_CPP
AC_PROG_INSTALL
AC_PROG_LN_S
AC_PROG_MAKE_SET
PKG_PROG_PKG_CONFIG

# Checks for libraries.
PKG_CHECK_MODULES([QMI], [qmi])
AC_SUBST([QMI_CFLAGS])
AC_SUBST([QMI_LIBS])

AC_ARG_WITH([qmux_libraries],
      AC_HELP_STRING([--with-qmux-libraries=@<:@dir@:>@],
         [Specify the location of the QMUXD libraries]),
      [qmux_libdir=$withval],
      with_qmux_libraries=no)

if test "x$with_qmux_libraries" != "xno"; then
   LDFLAGS="${LDFLAGS} -L${qmux_libdir}"
fi

AC_CONFIG_FILES([ \
        Makefile \
        common/src/Makefile \
        encdec/Makefile \
        qcci/src/Makefile \
        qcci/test/Makefile \
        qcsi/src/Makefile \
        qsap/src/Makefile \
        qcsi/test/Makefile \
        test_service/Makefile \
        qmi-framework.pc
        ])
AC_OUTPUT
