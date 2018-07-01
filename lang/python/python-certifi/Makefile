#
# Copyright (C) 2006-2011, 2015-2018 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=certifi
PKG_VERSION:=2018.4.16
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/4d/9c/46e950a6f4d6b4be571ddcae21e7bc846fcbb88f1de3eff0f6dd0a6be55d
PKG_HASH:=13e698f54293db9f89122b0581843a782ad0934a4fe0172d2a980ba77fc61bb7

PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-$(PKG_NAME)-$(PKG_VERSION)

PKG_MAINTAINER:=Weijie Gao <hackpascal@gmail.com>

include $(INCLUDE_DIR)/package.mk
include ../python-package.mk
include ../python3-package.mk

PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-component=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

define Package/python-certifi/Default
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  URL:=PKG_NAME
endef

define Package/python-certifi
$(call Package/python-certifi/Default)
  TITLE:=python-certifi
  DEPENDS:=+PACKAGE_python-certifi:python-light
  VARIANT:=python
endef

define Package/python3-certifi
$(call Package/python-certifi/Default)
  TITLE:=python3-certifi
  DEPENDS:=+PACKAGE_python3-certifi:python3-light
  VARIANT:=python3
endef

define Package/python-certifi/description
Certifi is a carefully curated collection of Root Certificates for
validating the trustworthiness of SSL certificates while verifying
the identity of TLS hosts. It has been extracted from the Requests
project.
endef

define Package/python3-certifi/description
$(call Package/python-certifi/description)
.
(Variant for Python3)
endef

$(eval $(call PyPackage,python-certifi))
$(eval $(call BuildPackage,python-certifi))
$(eval $(call BuildPackage,python-certifi-src))

$(eval $(call Py3Package,python3-certifi))
$(eval $(call BuildPackage,python3-certifi))
$(eval $(call BuildPackage,python3-certifi-src))
