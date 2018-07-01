#
# Copyright (C) 2006-2011, 2015-2018 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python-zope-proxy
PKG_VERSION:=4.3.0
PKG_RELEASE:=1

PKG_SOURCE:=zope.proxy-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/e6/a7/885eb04322fae6a382cdc484864ad153043df2c3c5397194298d1910b40b
PKG_HASH:=09b16e9644263d4ec9ade78fa0ae21590463a96eefe641150a184cd6931671ac

PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-zope-proxy-$(PKG_VERSION)

PKG_LICENSE:=ZPL-2.1
PKG_LICENSE_FILES:=LICENSE.txt
PKG_MAINTAINER:=Weijie Gao <hackpascal@gmail.com>

include $(INCLUDE_DIR)/package.mk
include ../python-package.mk
include ../python3-package.mk

PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-component=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

define Package/python-zope-proxy/Default
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  URL:=https://github.com/zopefoundation/zope.proxy
endef

define Package/python-zope-proxy
$(call Package/python-zope-proxy/Default)
  TITLE:=python-zope-proxy
  DEPENDS:=+PACKAGE_python-zope-proxy:python-zope-interface
  VARIANT:=python
endef

define Package/python3-zope-proxy
$(call Package/python-zope-proxy/Default)
  TITLE:=python3-zope-proxy
  DEPENDS:=+PACKAGE_python3-zope-proxy:python3-zope-interface
  VARIANT:=python3
endef

define Package/python-zope-proxy/description
zope.proxy is implemented via a C extension module
endef

define Package/python3-zope-proxy/description
$(call Package/python-zope-proxy/description)
.
(Variant for Python3)
endef

define PyPackage/python-zope-proxy/filespec
+|$(PYTHON_PKG_DIR)
-|$(PYTHON_PKG_DIR)/zope/proxy/_zope_proxy_proxy.c
-|$(PYTHON_PKG_DIR)/zope/proxy/proxy.h
endef

define Py3Package/python3-zope-proxy/filespec
+|$(PYTHON3_PKG_DIR)
-|$(PYTHON3_PKG_DIR)/zope/proxy/_zope_proxy_proxy.c
-|$(PYTHON3_PKG_DIR)/zope/proxy/proxy.h
endef

$(eval $(call PyPackage,python-zope-proxy))
$(eval $(call BuildPackage,python-zope-proxy))
$(eval $(call BuildPackage,python-zope-proxy-src))

$(eval $(call Py3Package,python3-zope-proxy))
$(eval $(call BuildPackage,python3-zope-proxy))
$(eval $(call BuildPackage,python3-zope-proxy-src))
