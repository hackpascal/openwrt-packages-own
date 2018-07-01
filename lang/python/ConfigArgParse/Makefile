#
# Copyright (C) 2018 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=ConfigArgParse
PKG_VERSION:=0.13.0
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/bw2/ConfigArgParse.git
PKG_SOURCE_VERSION:=$(PKG_VERSION)
PKG_MAINTAINER:=Weijie Gao <hackpascal@gmail.com>

PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-$(PKG_SOURCE_SUBDIR)
PKG_UNPACK=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

include $(INCLUDE_DIR)/package.mk
include ../python-package.mk
include ../python3-package.mk

define Package/python-configargparse/Default
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  URL:=https://github.com/bw2/ConfigArgParse/
endef

define Package/python-configargparse
$(call Package/python-configargparse/Default)
  TITLE:=ConfigArgParse
  DEPENDS:=+PACKAGE_python-configargparse:python-light
  VARIANT:=python
endef

define Package/python3-configargparse
$(call Package/python-configargparse/Default)
  TITLE:=ConfigArgParse (Python3)
  DEPENDS:=+PACKAGE_python3-configargparse:python3-light
  VARIANT:=python3
endef

define Package/python-configargparse/description
  Replacement for argparse with config files and environment
  variables
endef

define Package/python3-configargparse/description
$(call Package/python-configargparse/description)
  (Variant for Python3)
endef

$(eval $(call PyPackage,python-configargparse))
$(eval $(call BuildPackage,python-configargparse))
$(eval $(call BuildPackage,python-configargparse-src))

$(eval $(call Py3Package,python3-configargparse))
$(eval $(call BuildPackage,python3-configargparse))
$(eval $(call BuildPackage,python3-configargparse-src))
