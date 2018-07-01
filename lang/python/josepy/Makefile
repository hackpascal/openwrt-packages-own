#
# Copyright (C) 2018 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=josepy
PKG_VERSION:=1.1.0
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/certbot/josepy.git
PKG_SOURCE_VERSION:=v$(PKG_VERSION)
PKG_MAINTAINER:=Weijie Gao <hackpascal@gmail.com>

PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-$(PKG_SOURCE_SUBDIR)
PKG_UNPACK=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

include $(INCLUDE_DIR)/package.mk
include ../python-package.mk
include ../python3-package.mk

define Package/python-josepy/Default
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  URL:=https://github.com/certbot/josepy
endef

define Package/python-josepy
$(call Package/python-josepy/Default)
  TITLE:=JOSE protocol implementation in Python
  DEPENDS:= \
      +PACKAGE_python-josepy:python-light \
      +PACKAGE_python-josepy:python-cryptography \
      +PACKAGE_python-josepy:python-pyopenssl \
      +PACKAGE_python-josepy:python-six \
      +PACKAGE_python-josepy:python-setuptools
  VARIANT:=python
endef

define Package/python3-josepy
$(call Package/python-josepy/Default)
  TITLE:=JOSE protocol implementation in Python (Python3)
  DEPENDS:= \
      +PACKAGE_python3-josepy:python3-light \
      +PACKAGE_python3-josepy:python3-cryptography \
      +PACKAGE_python3-josepy:python3-pyopenssl \
      +PACKAGE_python3-josepy:python3-six \
      +PACKAGE_python3-josepy:python3-setuptools
  VARIANT:=python3
endef

define Package/python-josepy/description
  JOSE protocol implementation in Python
endef

define Package/python3-josepy/description
$(call Package/python-josepy/description)
  (Variant for Python3)
endef

define PyPackage/python-josepy/install
	$(INSTALL_DIR) $(1)/usr/bin $(1)/usr/lib/python$(PYTHON_VERSION)/site-packages
	# Adjust shebang to proper python location on target
	sed "1s@.*@#\!/usr/bin/python$(PYTHON_VERSION)@" -i $(PKG_INSTALL_DIR)/usr/bin/*
	$(CP) $(PKG_INSTALL_DIR)/usr/bin/* $(1)/usr/bin
	$(CP) \
		$(PKG_INSTALL_DIR)/usr/lib/* $(1)/usr/lib/
endef

define PyPackage/python3-josepy/install
	$(INSTALL_DIR) $(1)/usr/bin $(1)/usr/lib/python$(PYTHON3_VERSION)/site-packages
	# Adjust shebang to proper python location on target
	sed "1s@.*@#\!/usr/bin/python$(PYTHON3_VERSION)@" -i $(PKG_INSTALL_DIR)/usr/bin/*
	$(CP) $(PKG_INSTALL_DIR)/usr/bin/* $(1)/usr/bin
	$(CP) \
		$(PKG_INSTALL_DIR)/usr/lib/* $(1)/usr/lib/
endef

$(eval $(call PyPackage,python-josepy))
$(eval $(call BuildPackage,python-josepy))
$(eval $(call BuildPackage,python-josepy-src))

$(eval $(call Py3Package,python3-josepy))
$(eval $(call BuildPackage,python3-josepy))
$(eval $(call BuildPackage,python3-josepy-src))
