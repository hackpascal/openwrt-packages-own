#
# Copyright (C) 2018 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=pbr
PKG_VERSION:=4.0.4
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/cd/9f/8f14a51b522c47a315dd969fbdf39233e41f0bfa8b996b4ff0ad852ff43d
PKG_HASH:=a9c27eb8f0e24e786e544b2dbaedb729c9d8546342b5a6818d8eda098ad4340d
PKG_MAINTAINER:=Weijie Gao <hackpascal@gmail.com>

PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-$(PKG_SOURCE_SUBDIR)
PKG_UNPACK=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

include $(INCLUDE_DIR)/package.mk
include ../python-package.mk
include ../python3-package.mk

define Package/python-pbr/Default
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  URL:=https://docs.openstack.org/pbr/latest/
endef

define Package/python-pbr
$(call Package/python-pbr/Default)
  TITLE:=Python Build Reasonableness
  VARIANT:=python
  DEPENDS:=+PACKAGE_python-pbr:python-light
endef

define Package/python3-pbr
$(call Package/python-pbr/Default)
  TITLE:=Python Build Reasonableness (Python3)
  VARIANT:=python3
  DEPENDS:=+PACKAGE_python3-pbr:python3-light
endef

define Package/python-pbr/description
  PBR is a library that injects some useful and sensible default behaviors
  into your setuptools run.
endef

define Package/python3-pbr/description
$(call Package/python-pbr/description)
  (Variant for Python3)
endef

define PyPackage/python-pbr/install
	$(INSTALL_DIR) $(1)/usr/bin $(1)/usr/lib/python$(PYTHON_VERSION)/site-packages
	# Adjust shebang to proper python location on target
	sed "1s@.*@#\!/usr/bin/python$(PYTHON_VERSION)@" -i $(PKG_INSTALL_DIR)/usr/bin/*
	$(CP) $(PKG_INSTALL_DIR)/usr/bin/* $(1)/usr/bin
	$(CP) \
		$(PKG_INSTALL_DIR)/usr/lib/* $(1)/usr/lib/
endef

define PyPackage/python3-pbr/install
	$(INSTALL_DIR) $(1)/usr/bin $(1)/usr/lib/python$(PYTHON3_VERSION)/site-packages
	# Adjust shebang to proper python location on target
	sed "1s@.*@#\!/usr/bin/python$(PYTHON3_VERSION)@" -i $(PKG_INSTALL_DIR)/usr/bin/*
	$(CP) $(PKG_INSTALL_DIR)/usr/bin/* $(1)/usr/bin
	$(CP) \
		$(PKG_INSTALL_DIR)/usr/lib/* $(1)/usr/lib/
endef

$(eval $(call PyPackage,python-pbr))
$(eval $(call BuildPackage,python-pbr))
$(eval $(call BuildPackage,python-pbr-src))

$(eval $(call Py3Package,python3-pbr))
$(eval $(call BuildPackage,python3-pbr))
$(eval $(call BuildPackage,python3-pbr-src))
