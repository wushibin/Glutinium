#
# Copyright (C) 2006-2018 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=libxsonrpc
PKG_VERSION:=0.1
PKG_RELEASE:=1
PKG_MAINTAINER:=Igor Zalatov <flyrouter@gmail.com>

PKG_LICENSE:=GPL-2.0
PKG_LICENSE_FILES:=LICENSE

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/$(PKG_NAME)
	SECTION:=openipc
	CATEGORY:=OpenIPC
	TITLE:=A simple server handling both XML-RPC and JSON-RPC
	MAINTAINER:=Sharshunov Sergey <ssharshunov@github.com>
	DEPENDS:=+hisi-osdrv2-lib
endef

define Package/$(PKG_NAME)/description
	A simple server handling both XML-RPC and JSON-RPC
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
	$(CP) ./src/* $(PKG_BUILD_DIR)/
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/*.so $(1)/usr/lib/
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
