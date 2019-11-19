# Copyright (C) 2016 LEDE project

include $(TOPDIR)/rules.mk

PKG_NAME:=openwrt-keyring
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL=$(PROJECT_GIT)/keyring.git
PKG_SOURCE_DATE:=2019-07-24
PKG_SOURCE_VERSION:=228f8dad591f61166578dbbfdc5aa7ba93e00b62
PKG_MIRROR_HASH:=915dd98afa97f9ebfd2d857ec865280e10ae8020856d69977a4c641c9dfcbe42

PKG_MAINTAINER:=John Crispin <john@phrozen.org>
PKG_LICENSE:=GPL-2.0

include $(INCLUDE_DIR)/package.mk

define Package/openwrt-keyring
  SECTION:=base
  CATEGORY:=Base system
  PROVIDES:=lede-keyring
  TITLE:=OpenWrt Developer Keyring
  URL:=https://openwrt.org/docs/guide-user/security/signatures
endef

define Package/openwrt-keyring/description
  The keyring of with the developer using and gpg public keys.
endef

Build/Compile=

define Package/openwrt-keyring/install
	$(INSTALL_DIR) $(1)/etc/opkg/keys/
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/usign/* $(1)/etc/opkg/keys/
endef

$(eval $(call BuildPackage,openwrt-keyring))
