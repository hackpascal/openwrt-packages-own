#
# Copyright (C) 2018 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python-acme
PKG_VERSION:=0.25.1
PKG_RELEASE:=1

PKG_SOURCE:=certbot-$(PKG_VERSION).tar.gz
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/certbot/certbot.git
PKG_SOURCE_VERSION:=v$(PKG_VERSION)
PKG_MAINTAINER:=Weijie Gao <hackpascal@gmail.com>

PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_SOURCE_SUBDIR)
PKG_UNPACK=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=2 -xzf $(DL_DIR)/$(PKG_SOURCE) certbot-$(PKG_VERSION)/acme

include $(INCLUDE_DIR)/package.mk
include ../python-package.mk

define Package/python-acme
  SECTION:=net
  CATEGORY:=Network
  URL:=https://certbot.eff.org
  TITLE:=Client of Let's Encrypt
  VARIANT:=python
  DEPENDS:= \
      +PACKAGE_certbot:python-cryptography \
      +PACKAGE_certbot:python-josepy \
      +PACKAGE_certbot:mock \
      +PACKAGE_certbot:python-pyopenssl \
      +PACKAGE_certbot:python-pyrfc3339 \
      +PACKAGE_certbot:pytz \
      +PACKAGE_certbot:python-setuptools \
      +PACKAGE_certbot:python-six \
      +PACKAGE_certbot:python-requests \
      +PACKAGE_certbot:python-requests-toolbelt
endef

define Package/python-acme/description
  Certbot is part of EFF's effort to encrypt the entire Internet.
  Secure communication over the Web relies on HTTPS, which requires the
  use of a digital certificate that lets browsers verify the identity of
  web servers. Certbot is an easy-to-use client that fetches a certificate
  from Let’s Encrypt—an open certificate authority launched by the EFF,
  Mozilla, and others—and deploys it to a web server.
endef

$(eval $(call PyPackage,python-acme))
$(eval $(call BuildPackage,python-acme))
$(eval $(call BuildPackage,python-acme-src))
