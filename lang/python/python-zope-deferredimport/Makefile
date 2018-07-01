#
# Copyright (C) 2006-2011, 2015-2018 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python-zope-deferredimport
PKG_VERSION:=4.2.1
PKG_RELEASE:=1

PKG_SOURCE:=zope.deferredimport-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/f8/84/77c2feaeaed546129fbd2fd3267bacf64f6770bd2832e561af870e08e7ac
PKG_HASH:=964b32352ed7c5cf2d02af4088a523845ca386256f3ab2d2c6e2b96a97eca758

PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-zope-deferredimport-$(PKG_VERSION)

PKG_LICENSE:=ZPL-2.1
PKG_LICENSE_FILES:=LICENSE.txt
PKG_MAINTAINER:=Weijie Gao <hackpascal@gmail.com>

include $(INCLUDE_DIR)/package.mk
include ../python-package.mk
include ../python3-package.mk

PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-component=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

define Package/python-zope-deferredimport/Default
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  URL:=https://github.com/zopefoundation/zope.deferredimport
endef

define Package/python-zope-deferredimport
$(call Package/python-zope-deferredimport/Default)
  TITLE:=python-zope-deferredimport
  DEPENDS:=+PACKAGE_python-zope-deferredimport:python-zope-proxy
  VARIANT:=python
endef

define Package/python3-zope-deferredimport
$(call Package/python-zope-deferredimport/Default)
  TITLE:=python3-zope-deferredimport
  DEPENDS:=+PACKAGE_python3-zope-deferredimport:python3-zope-proxy
  VARIANT:=python3
endef

define Package/python-zope-deferredimport/description
The zope.deferredimport package provided facilities for defining
names in modules that will be imported from somewhere else when used.
You can also cause deprecation warnings to be issued when a variable is used.
endef

define Package/python3-zope-deferredimport/description
$(call Package/python-zope-deferredimport/description)
.
(Variant for Python3)
endef

$(eval $(call PyPackage,python-zope-deferredimport))
$(eval $(call BuildPackage,python-zope-deferredimport))
$(eval $(call BuildPackage,python-zope-deferredimport-src))

$(eval $(call Py3Package,python3-zope-deferredimport))
$(eval $(call BuildPackage,python3-zope-deferredimport))
$(eval $(call BuildPackage,python3-zope-deferredimport-src))
