#
# Copyright (C) 2006-2011, 2015-2018 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python-zope-event
PKG_VERSION:=4.3.0
PKG_RELEASE:=1

PKG_SOURCE:=zope.event-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/9e/d0/54ba59f19a0635f6591b74be259cf6fbf67e73f4edda27b5cd0cf4d26efa
PKG_HASH:=e0ecea24247a837c71c106b0341a7a997e3653da820d21ef6c08b32548f733e7

PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-zope-event-$(PKG_VERSION)

PKG_LICENSE:=ZPL-2.1
PKG_LICENSE_FILES:=LICENSE.txt
PKG_MAINTAINER:=Weijie Gao <hackpascal@gmail.com>

include $(INCLUDE_DIR)/package.mk
include ../python-package.mk
include ../python3-package.mk

PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-component=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

define Package/python-zope-event/Default
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  URL:=https://github.com/zopefoundation/zope.event
endef

define Package/python-zope-event
$(call Package/python-zope-event/Default)
  TITLE:=python-zope-event
  DEPENDS:= \
      +PACKAGE_python-zope-event:python-setuptools \
      +PACKAGE_python-zope-event:python-light
  VARIANT:=python
endef

define Package/python3-zope-event
$(call Package/python-zope-event/Default)
  TITLE:=python3-zope-event
  DEPENDS:= \
      +PACKAGE_python3-zope-event:python3-setuptools \
      +PACKAGE_python3-zope-event:python3-light
  VARIANT:=python3
endef

define Package/python-zope-event/description
The zope.event package provides a simple event system
endef

define Package/python3-zope-event/description
$(call Package/python-zope-event/description)
.
(Variant for Python3)
endef

$(eval $(call PyPackage,python-zope-event))
$(eval $(call BuildPackage,python-zope-event))
$(eval $(call BuildPackage,python-zope-event-src))

$(eval $(call Py3Package,python3-zope-event))
$(eval $(call BuildPackage,python3-zope-event))
$(eval $(call BuildPackage,python3-zope-event-src))
