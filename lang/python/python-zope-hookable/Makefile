#
# Copyright (C) 2006-2011, 2015-2018 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python-zope-hookable
PKG_VERSION:=4.2.0
PKG_RELEASE:=1

PKG_SOURCE:=zope.hookable-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/41/b5/378175b959565de41f45c775cdfbf8897aaeaf29a258b94e40bd2661ce46
PKG_HASH:=c1df3929a3666fc5a0c80d60a0c1e6f6ef97c7f6ed2f1b7cf49f3e6f3d4dde15

PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-zope-hookable-$(PKG_VERSION)

PKG_LICENSE:=ZPL-2.1
PKG_LICENSE_FILES:=LICENSE.txt
PKG_MAINTAINER:=Weijie Gao <hackpascal@gmail.com>

include $(INCLUDE_DIR)/package.mk
include ../python-package.mk
include ../python3-package.mk

PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-component=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

define Package/python-zope-hookable/Default
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  URL:=https://github.com/zopefoundation/zope.hookable
endef

define Package/python-zope-hookable
$(call Package/python-zope-hookable/Default)
  TITLE:=python-zope-hookable
  DEPENDS:=+PACKAGE_python-zope-hookable:python-setuptools
  VARIANT:=python
endef

define Package/python3-zope-hookable
$(call Package/python-zope-hookable/Default)
  TITLE:=python3-zope-hookable
  DEPENDS:=+PACKAGE_python3-zope-hookable:python3-setuptools
  VARIANT:=python3
endef

define Package/python-zope-hookable/description
This package supports the efficient creation of “hookable” objects,
which are callable objects that are meant to be optionally replaced.
endef

define Package/python3-zope-hookable/description
$(call Package/python-zope-hookable/description)
.
(Variant for Python3)
endef

define PyPackage/python-zope-hookable/filespec
+|$(PYTHON_PKG_DIR)
-|$(PYTHON_PKG_DIR)/zope/hookable/_zope_hookable.c
endef

define Py3Package/python3-zope-hookable/filespec
+|$(PYTHON3_PKG_DIR)
-|$(PYTHON3_PKG_DIR)/zope/hookable/_zope_hookable.c
endef

$(eval $(call PyPackage,python-zope-hookable))
$(eval $(call BuildPackage,python-zope-hookable))
$(eval $(call BuildPackage,python-zope-hookable-src))

$(eval $(call Py3Package,python3-zope-hookable))
$(eval $(call BuildPackage,python3-zope-hookable))
$(eval $(call BuildPackage,python3-zope-hookable-src))
