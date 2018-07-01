#
# Copyright (C) 2006-2011, 2015-2018 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python-zope-deprecation
PKG_VERSION:=4.3.0
PKG_RELEASE:=1

PKG_SOURCE:=zope.deprecation-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/a1/18/2dc5e6bfe64fdc3b79411b67464c55bb0b43b127051a20f7f492ab767758
PKG_HASH:=7d52e134bbaaa0d72e1e2bc90f0587f1adc116c4bdf15912afaf2f1e8856b224

PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-zope-deprecation-$(PKG_VERSION)

PKG_LICENSE:=ZPL-2.1
PKG_LICENSE_FILES:=LICENSE.txt
PKG_MAINTAINER:=Weijie Gao <hackpascal@gmail.com>

include $(INCLUDE_DIR)/package.mk
include ../python-package.mk
include ../python3-package.mk

PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-component=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

define Package/python-zope-deprecation/Default
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  URL:=https://github.com/zopefoundation/zope.deprecation
endef

define Package/python-zope-deprecation
$(call Package/python-zope-deprecation/Default)
  TITLE:=python-zope-deprecation
  DEPENDS:= \
      +PACKAGE_python-zope-deprecation:python-setuptools \
      +PACKAGE_python-zope-deprecation:python-light
  VARIANT:=python
endef

define Package/python3-zope-deprecation
$(call Package/python-zope-deprecation/Default)
  TITLE:=python3-zope-deprecation
  DEPENDS:= \
      +PACKAGE_python3-zope-deprecation:python3-setuptools \
      +PACKAGE_python3-zope-deprecation:python3-light
  VARIANT:=python3
endef

define Package/python-zope-deprecation/description
This package provides a simple function called deprecated(names, reason)
to mark deprecated modules, classes, functions, methods and properties.
endef

define Package/python3-zope-deprecation/description
$(call Package/python-zope-deprecation/description)
.
(Variant for Python3)
endef

$(eval $(call PyPackage,python-zope-deprecation))
$(eval $(call BuildPackage,python-zope-deprecation))
$(eval $(call BuildPackage,python-zope-deprecation-src))

$(eval $(call Py3Package,python3-zope-deprecation))
$(eval $(call BuildPackage,python3-zope-deprecation))
$(eval $(call BuildPackage,python3-zope-deprecation-src))
