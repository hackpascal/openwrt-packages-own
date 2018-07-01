#
# Copyright (C) 2018 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=pyrfc3339
PKG_VERSION:=1.1
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/kurtraschke/pyRFC3339.git
PKG_SOURCE_VERSION:=v$(PKG_VERSION)
PKG_MAINTAINER:=Weijie Gao <hackpascal@gmail.com>

PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-$(PKG_SOURCE_SUBDIR)
PKG_UNPACK=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

include $(INCLUDE_DIR)/package.mk
include ../python-package.mk
include ../python3-package.mk

define Package/python-pyrfc3339/Default
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  URL:=https://github.com/kurtraschke/pyRFC3339
endef

define Package/python-pyrfc3339
$(call Package/python-pyrfc3339/Default)
  TITLE:=Generating and parsing RFC 3339-compliant timestamps
  VARIANT:=python
  DEPENDS:= \
      +PACKAGE_python-pyrfc3339:pytz \
      +PACKAGE_python-pyrfc3339:python-light
endef

define Package/python3-pyrfc3339
$(call Package/python-pyrfc3339/Default)
  TITLE:=Generating and parsing RFC 3339-compliant timestamps (Python3)
  VARIANT:=python3
  DEPENDS:= \
      +PACKAGE_python3-pyrfc3339:python3-pytz \
      +PACKAGE_python3-pyrfc3339:python3-light
endef

define Package/python-pyrfc3339/description
  Python library for generating and parsing RFC 3339-compliant timestamps.
endef

define Package/python3-pyrfc3339/description
$(call Package/python-pyrfc3339/description)
  (Variant for Python3)
endef

$(eval $(call PyPackage,python-pyrfc3339))
$(eval $(call BuildPackage,python-pyrfc3339))
$(eval $(call BuildPackage,python-pyrfc3339-src))

$(eval $(call Py3Package,python3-pyrfc3339))
$(eval $(call BuildPackage,python3-pyrfc3339))
$(eval $(call BuildPackage,python3-pyrfc3339-src))
