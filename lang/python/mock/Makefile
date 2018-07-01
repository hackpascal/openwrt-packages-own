#
# Copyright (C) 2018 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=mock
PKG_VERSION:=2.0.0
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/testing-cabal/mock.git
PKG_SOURCE_VERSION:=$(PKG_VERSION)
PKG_MAINTAINER:=Weijie Gao <hackpascal@gmail.com>

PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-$(PKG_NAME)-$(PKG_VERSION)
PKG_UNPACK=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

include $(INCLUDE_DIR)/package.mk
include ../python-package.mk

define Package/mock
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  URL:=https://github.com/testing-cabal/mock
  TITLE:=The Python mock library
  DEPENDS:= \
      +PACKAGE_mock:python-light \
      +PACKAGE_mock:python-pbr \
      +PACKAGE_mock:python-funcsigs \
      +PACKAGE_mock:python-setuptools
  VARIANT:=python
endef

define Package/mock/description
  Mock is a library for testing in Python. It allows you to replace parts
  of your system under test with mock objects and make assertions about
  how they have been used.
endef

$(eval $(call PyPackage,mock))
$(eval $(call BuildPackage,mock))
$(eval $(call BuildPackage,mock-src))
