dnl Copyright (c) 2016 Moriyoshi Koizumi
dnl 
dnl Permission is hereby granted, free of charge, to any person obtaining a
dnl copy of this software and associated documentation files (the "Software"),
dnl to deal in the Software without restriction, including without limitation
dnl the rights to use, copy, modify, merge, publish, distribute, sublicense,
dnl and/or sell copies of the Software, and to permit persons to whom the
dnl Software is furnished to do so, subject to the following conditions:
dnl 
dnl The above copyright notice and this permission notice shall be included in
dnl all copies or substantial portions of the Software.
dnl 
dnl THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
dnl IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
dnl FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
dnl AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
dnl LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
dnl FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER
dnl DEALINGS IN THE SOFTWARE.

AC_INIT([cyrus-sasl-xoauth2], [0.0])
AM_INIT_AUTOMAKE
AC_CONFIG_MACRO_DIR([m4])
LT_INIT
AC_PROG_CC
AC_CONFIG_HEADERS([config.h])
AC_CONFIG_FILES([Makefile])

# Cygwin stuff
case "$host" in
  *-*-cygwin*)
    CYRUS_SASL_LDFLAGS=-no-undefined
    ;;
esac

PKG_PROG_PKG_CONFIG
PKG_CHECK_MODULES([CYRUS_SASL], [libsasl2],, [AC_MSG_ERROR([Cyrus-SASL not found])])
CYRUS_SASL_LIBDIR=$($PKG_CONFIG --variable=libdir libsasl2)

AC_SUBST([CYRUS_SASL_LDFLAGS], [$CYRUS_SASL_LDFLAGS])
AC_SUBST(CYRUS_SASL_LIBDIR)
AC_OUTPUT
