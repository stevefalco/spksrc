PKG_NAME = bacula
PKG_VERS = 11.0.6
PKG_EXT = tar.gz
PKG_DIST_NAME = $(PKG_NAME)-$(PKG_VERS).$(PKG_EXT)
PKG_DIST_SITE = https://download.sourceforge.net/$(PKG_NAME)
PKG_DIR = $(PKG_NAME)-$(PKG_VERS)

DEPENDS = cross/openssl

HOMEPAGE = https://www.bacula.org/
COMMENT  = Bacula is an open source backup system
LICENSE  = AGPLv3

GNU_CONFIGURE = 1
CONFIGURE_ARGS = --enable-client-only --with-working-dir=$(INSTALL_PREFIX)/var/bacula ac_cv_func_setpgrp_void=yes

ifeq ($(findstring $(ARCH), ppc824x ppc853x),$(ARCH))
ifneq (5,$(firstword $(sort $(TCVERSION) 5)))
# toolchains before version 5 require the old linux quota version
# related issue: https://github.com/transmission/transmission/issues/591
ADDITIONAL_CFLAGS = -D_LINUX_QUOTA_VERSION=1
endif
endif


include ../../mk/spksrc.cross-cc.mk
