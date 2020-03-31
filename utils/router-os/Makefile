# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information. kmod-fs-exfat

include $(TOPDIR)/rules.mk

PKG_NAME:=router-os
PKG_RELEASE:=1

include $(INCLUDE_DIR)/package.mk

define Package/router-os
  SECTION:=utils
  CATEGORY:=Utilities
	TITLE:= Router OS configuration
	URL:=https://bacnh.com
	DEPENDS:=+luci-ssl-nginx +luci-app-ddns +luci-app-openvpn +htop +luci-app-sqm
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
endef

define Build/Compile
       
endef

define Package/router-os/install

	$(CP) ./files/* $(1)
endef

$(eval $(call BuildPackage,router-os))