#
# Copyright (C) 2007-2018 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python3-pytz
PKG_VERSION:=2018.4
PKG_RELEASE:=1
PKG_LICENSE:=MIT

PKG_SOURCE:=pytz-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/10/76/52efda4ef98e7544321fd8d5d512e11739c1df18b0649551aeccfb1c8376
PKG_HASH:=c06425302f2cf668f1bba7a0a03f3c1d34d4ebeef2c72003da308b3947c7f749

PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-pytz-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
include ../python3-package.mk

PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

define Package/python3-pytz
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  MAINTAINER:=Gergely Kiss <mail.gery@gmail.com>
  TITLE:=World timezone definitions, modern and historical (Python 3)
  URL:=https://sourceforge.net/projects/pytz/
  DEPENDS:=+PACKAGE_python3-pytz:python3-light
  VARIANT:=python3
endef

define Package/python3-pytz/description
  World timezone definitions, modern and historical
endef

$(eval $(call Py3Package,python3-pytz))
$(eval $(call BuildPackage,python3-pytz))
$(eval $(call BuildPackage,python3-pytz-src))
