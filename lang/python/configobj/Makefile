#
# Copyright (C) 2018 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=configobj
PKG_VERSION:=5.0.6
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/DiffSK/configobj.git
PKG_SOURCE_VERSION:=v$(PKG_VERSION)
PKG_MAINTAINER:=Weijie Gao <hackpascal@gmail.com>

PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-$(PKG_SOURCE_SUBDIR)
PKG_UNPACK=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

include $(INCLUDE_DIR)/package.mk
include ../python-package.mk
include ../python3-package.mk

define Package/python-configobj/Default
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  URL:=https://github.com/DiffSK/configobj
endef

define Package/python-configobj
$(call Package/python-configobj/Default)
  TITLE:=configobj
  DEPENDS:= \
      +PACKAGE_python-configobj:python-light \
      +PACKAGE_python-configobj:python-six
  VARIANT:=python
endef

define Package/python3-configobj
$(call Package/python-configobj/Default)
  TITLE:=configobj (Python3)
  DEPENDS:= \
      +PACKAGE_python3-configobj:python3-light \
      +PACKAGE_python3-configobj:python3-six
  VARIANT:=python3
endef

define Package/python-configobj/description
  ConfigObj is a simple but powerful config file reader and writer - an
  ini file round tripper. Its main feature is that it is very easy to use,
  with a straightforward programmer’s interface and a simple syntax for
  config files.
endef

define Package/python3-configobj/description
$(call Package/python-configobj/description)
  (Variant for Python3)
endef

define PyBuild/Compile
	$(call Build/Compile/PyMod,,install --prefix="/usr" --root="$(PKG_INSTALL_DIR)",)
endef

define Py3Build/Compile
	$(call Build/Compile/Py3Mod,,install --prefix="/usr" --root="$(PKG_INSTALL_DIR)",)
endef

$(eval $(call PyPackage,python-configobj))
$(eval $(call BuildPackage,python-configobj))
$(eval $(call BuildPackage,python-configobj-src))

$(eval $(call Py3Package,python3-configobj))
$(eval $(call BuildPackage,python3-configobj))
$(eval $(call BuildPackage,python3-configobj-src))
