#
# Copyright (C) 2018 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=requests
PKG_VERSION:=2.19.1
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/requests/requests.git
PKG_SOURCE_VERSION:=v$(PKG_VERSION)
PKG_MAINTAINER:=Weijie Gao <hackpascal@gmail.com>

PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-$(PKG_SOURCE_SUBDIR)
PKG_UNPACK=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

include $(INCLUDE_DIR)/package.mk
include ../python-package.mk

define Package/python-requests
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  URL:=http://python-requests.org/
  TITLE:=Python HTTP Requests for Humans
  DEPENDS:= \
      +PACKAGE_python-requests:python-light \
      +PACKAGE_python-requests:chardet \
      +PACKAGE_python-requests:python-idna \
      +PACKAGE_python-requests:python-urllib3 \
      +PACKAGE_python-requests:python-certifi \
      +PACKAGE_python-requests:python-pyopenssl \
      +PACKAGE_python-requests:python-cryptography
  VARIANT:=python
endef

define Package/python-requests/description
  Requests is the only Non-GMO HTTP library for Python, safe for
  human consumption.
endef

$(eval $(call PyPackage,python-requests))
$(eval $(call BuildPackage,python-requests))
$(eval $(call BuildPackage,python-requests-src))
