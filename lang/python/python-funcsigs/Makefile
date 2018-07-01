#
# Copyright (C) 2006-2011, 2015-2018 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=funcsigs
PKG_VERSION:=1.0.2
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/94/4a/db842e7a0545de1cdb0439bb80e6e42dfe82aaeaadd4072f2263a4fbed23
PKG_HASH:=a7bb0f2cf3a3fd1ab2732cb49eba4252c2af4240442415b4abce3b87022a8f50

PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-$(PKG_NAME)-$(PKG_VERSION)

PKG_MAINTAINER:=Weijie Gao <hackpascal@gmail.com>

include $(INCLUDE_DIR)/package.mk
include ../python-package.mk

PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-component=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

define Package/python-funcsigs/Default
endef

define Package/python-funcsigs
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  URL:=http://funcsigs.readthedocs.org/
  TITLE:=python-funcsigs
  DEPENDS:=+PACKAGE_python-funcsigs:python-setuptools
  VARIANT:=python
endef

define Package/python-funcsigs/description
  funcsigs is a backport of the PEP 362 function signature features
  from Python 3.3’s inspect module.
endef

$(eval $(call PyPackage,python-funcsigs))
$(eval $(call BuildPackage,python-funcsigs))
$(eval $(call BuildPackage,python-funcsigs-src))
