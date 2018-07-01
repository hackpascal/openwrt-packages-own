#
# Copyright (C) 2018 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=toolbelt
PKG_VERSION:=0.8.0
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/requests/toolbelt.git
PKG_SOURCE_VERSION:=$(PKG_VERSION)
PKG_MAINTAINER:=Weijie Gao <hackpascal@gmail.com>

PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-$(PKG_SOURCE_SUBDIR)
PKG_UNPACK=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

include $(INCLUDE_DIR)/package.mk
include ../python-package.mk

define Package/python-requests-toolbelt
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  URL:=https://toolbelt.readthedocs.org/
  TITLE:=python-requests-toolbelt
  DEPENDS:=+PACKAGE_python-requests-toolbelt:python-requests
  VARIANT:=python
endef

define Package/python-requests-toolbelt/description
  A toolbelt of useful classes and functions to be used with python-requests.
endef

$(eval $(call PyPackage,python-requests-toolbelt))
$(eval $(call BuildPackage,python-requests-toolbelt))
$(eval $(call BuildPackage,python-requests-toolbelt-src))
