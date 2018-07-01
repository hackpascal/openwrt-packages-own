#
# Copyright (C) 2018 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=future
PKG_VERSION:=0.16.0
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/00/2b/8d082ddfed935f3608cc61140df6dcbf0edea1bc3ab52fb6c29ae3e81e85/
PKG_HASH:=e39ced1ab767b5936646cedba8bcce582398233d6a627067d4c6a454c90cfedb
PKG_MAINTAINER:=Weijie Gao <hackpascal@gmail.com>

PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-$(PKG_SOURCE_SUBDIR)
PKG_UNPACK=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

include $(INCLUDE_DIR)/package.mk
include ../python-package.mk
include ../python3-package.mk

define Package/python-future/Default
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  URL:=https://pypi.org/project/future/
endef

define Package/python-future
$(call Package/python-future/Default)
  TITLE:=A compatibility layer between Python 2 and Python 3
  VARIANT:=python
  DEPENDS:=+PACKAGE_python-future:python-light
endef

define Package/python3-future
$(call Package/python-future/Default)
  TITLE:=A compatibility layer between Python 2 and Python 3 (Python3)
  VARIANT:=python3
  DEPENDS:=+PACKAGE_python3-future:python3-light
endef

define Package/python-future/description
  future is the missing compatibility layer between Python 2 and Python 3.
  It allows you to use a single, clean Python 3.x-compatible codebase to
  support both Python 2 and Python 3 with minimal overhead.
endef

define Package/python3-future/description
$(call Package/python-future/description)
  (Variant for Python3)
endef

$(eval $(call PyPackage,python-future))
$(eval $(call BuildPackage,python-future))
$(eval $(call BuildPackage,python-future-src))

$(eval $(call Py3Package,python3-future))
$(eval $(call BuildPackage,python3-future))
$(eval $(call BuildPackage,python3-future-src))
