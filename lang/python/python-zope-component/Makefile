#
# Copyright (C) 2006-2011, 2015-2018 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python-zope-component
PKG_VERSION:=4.4.1
PKG_RELEASE:=1

PKG_SOURCE:=zope.component-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/45/3c/bd34f228e2ff303071b5ff68657abf6d11af2151056acd449796eff694e0
PKG_HASH:=1b29aa65413f6dda29e64e2352a6aa13d9ba70078f6b91f328573488788d531c

PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-zope-component-$(PKG_VERSION)

PKG_LICENSE:=ZPL-2.1
PKG_LICENSE_FILES:=LICENSE.txt
PKG_MAINTAINER:=Weijie Gao <hackpascal@gmail.com>

include $(INCLUDE_DIR)/package.mk
include ../python-package.mk
include ../python3-package.mk

PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

define Package/python-zope-component/Default
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  URL:=https://github.com/zopefoundation/zope.component
endef

define Package/python-zope-component
$(call Package/python-zope-component/Default)
  TITLE:=python-zope-component
  DEPENDS:= \
      +PACKAGE_python-zope-component:python-zope-deferredimport \
      +PACKAGE_python-zope-component:python-zope-deprecation \
      +PACKAGE_python-zope-component:python-zope-event \
      +PACKAGE_python-zope-component:python-zope-hookable \
      +PACKAGE_python-zope-component:python-zope-interface \
      +PACKAGE_python-zope-component:python-light
  VARIANT:=python
endef

define Package/python3-zope-component
$(call Package/python-zope-component/Default)
  TITLE:=python3-zope-component
  DEPENDS:= \
      +PACKAGE_python3-zope-component:python3-zope-deferredimport \
      +PACKAGE_python3-zope-component:python3-zope-deprecation \
      +PACKAGE_python3-zope-component:python3-zope-event \
      +PACKAGE_python3-zope-component:python3-zope-hookable \
      +PACKAGE_python3-zope-component:python3-zope-interface \
      +PACKAGE_python3-zope-component:python3-light
  VARIANT:=python3
endef

define Package/python-zope-component/description
This package represents the core of the Zope Component Architecture.
Together with the zope.interface package, it provides facilities for
defining, registering and looking up components.
endef

define Package/python3-zope-component/description
$(call Package/python-zope-component/description)
.
(Variant for Python3)
endef

$(eval $(call PyPackage,python-zope-component))
$(eval $(call BuildPackage,python-zope-component))
$(eval $(call BuildPackage,python-zope-component-src))

$(eval $(call Py3Package,python3-zope-component))
$(eval $(call BuildPackage,python3-zope-component))
$(eval $(call BuildPackage,python3-zope-component-src))
