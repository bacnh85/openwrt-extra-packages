#
# Copyright (C) 2006-2018 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=paho.mqtt.c
PKG_VERSION:=1.3.0
PKG_RELEASE:=1

PKG_SOURCE:=v$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/eclipse/paho.mqtt.c/archive/
PKG_MD5SUM:=8fac1bff9b0d5a74fa1caf8db0501fca

PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=COPYING

PKG_FIXUP:=autoreconf
PKG_INSTALL:=1

PKG_MAINTAINER:=HaiBac Ngo <ngohaibac@gmail.com>

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

CMAKE_OPTIONS = -DPAHO_BUILD_SAMPLES=TRUE -DPAHO_WITH_SSL=TRUE

TARGET_CFLAGS += $(FPIC)

define Package/libpaho.mqtt.c
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE:= Eclipse Paho MQTT C client
  URL:=http://eclipse.org/paho
  DEPENDS:=+libpthread +libcrypto +libopenssl
endef

define Package/libpaho.mqtt.c/description
  Eclipse Paho MQTT C client
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include
	$(CP) $(PKG_INSTALL_DIR)/usr/include/MQTT*.h $(1)/usr/include/
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libpaho-mqtt3*.so* $(1)/usr/lib/	
endef

define Package/libpaho.mqtt.c/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libpaho-mqtt3*.so* $(1)/usr/lib/	
endef

$(eval $(call BuildPackage,libpaho.mqtt.c))