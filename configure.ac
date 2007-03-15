AC_PREREQ(2.50)

AC_INIT(couriersrs.h)
AM_INIT_AUTOMAKE(couriersrs,0.0.1)
AM_CONFIG_HEADER(config.h)
AC_LANG(C++)
AC_GNU_SOURCE

sinclude(ac-helpers/ac_define_dir.m4)

dnl Check for programs
AC_PROG_CC
AC_PROG_INSTALL
AC_PROG_MAKE_SET
AM_ICONV

AM_GNU_GETTEXT
AM_GNU_GETTEXT_VERSION(0.14.1)
ALL_LINGUAS=""

AC_DISABLE_STATIC
AC_PROG_LIBTOOL
AC_SUBST(LIBTOOL_DEPS)

AC_SUBST([localedir], ['${datadir}/locale'])

dnl use libtool to compile checks (particularly lib checks), mostly so we don't have to worry about how/if the os supports -R
ac_link="${SHELL} ${srcdir}/libtool --mode=link $ac_link"

dnl headers we need
AC_HEADER_STDC

dnl static builds
AC_MSG_CHECKING(if static builds enabled)
AC_ARG_ENABLE(all-static, AC_HELP_STRING([--enable-all-static], [Build static binaries]), all_static=yes, all_static=no)
if test "x-$all_static" = "x-yes" ; then
    LDFLAGS="$LDFLAGS -Wl,-static -static"
fi
AC_MSG_RESULT($all_static)

AC_MSG_CHECKING(if partial static builds enabled)
AC_ARG_ENABLE(partial-static, AC_HELP_STRING([--enable-partial-static], [Build partially static binaries]), partial_static=yes, partial_static=no)
if test "x-$partial_static" = "x-yes" ; then
    LDFLAGS="$LDFLAGS -Wl,-lc,-static -static"
fi
AC_MSG_RESULT($partial_static)

AC_DEFINE_DIR(LOCALSTATEDIR, localstatedir, [base where spool can be found])

dnl Create the makefiles
AC_OUTPUT(Makefile intl/Makefile po/Makefile.in m4/Makefile )
