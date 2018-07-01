#
# Copyright (C) 2018 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=parsedatetime
PKG_VERSION:=2.4
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/bear/parsedatetime.git
PKG_SOURCE_VERSION:=v$(PKG_VERSION)
PKG_MAINTAINER:=Weijie Gao <hackpascal@gmail.com>

PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-$(PKG_SOURCE_SUBDIR)
PKG_UNPACK=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

include $(INCLUDE_DIR)/package.mk
include ../python-package.mk
include ../python3-package.mk

define Package/python-parsedatetime/Default
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  URL:=https://github.com/bear/parsedatetime
endef

define Package/python-parsedatetime
$(call Package/python-parsedatetime/Default)
  TITLE:=Parse human-readable date/time strings
  VARIANT:=python
  DEPENDS:= \
      +PACKAGE_python-parsedatetime:python-future \
      +PACKAGE_python-parsedatetime:python-light
endef

define Package/python3-parsedatetime
$(call Package/python-parsedatetime/Default)
  TITLE:=Parse human-readable date/time strings (Python3)
  VARIANT:=python3
  DEPENDS:= \
      +PACKAGE_python3-parsedatetime:python3-future \
      +PACKAGE_python3-parsedatetime:python3-light
endef

define Package/python-parsedatetime/description
  Parse human-readable date/time strings
endef

define Package/python3-parsedatetime/description
$(call Package/python-parsedatetime/description)
  (Variant for Python3)
endef

$(eval $(call PyPackage,python-parsedatetime))
$(eval $(call BuildPackage,python-parsedatetime))
$(eval $(call BuildPackage,python-parsedatetime-src))

$(eval $(call Py3Package,python3-parsedatetime))
$(eval $(call BuildPackage,python3-parsedatetime))
$(eval $(call BuildPackage,python3-parsedatetime-src))
