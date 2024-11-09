include $(TOPDIR)/rules.mk

PKG_NAME:=srtla
PKG_VERSION:=f138fb4
PKG_RELEASE:=1
PKG_URL:=https://github.com/BELABOX/srtla

include $(INCLUDE_DIR)/package.mk

define Package/srtla
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=SRTLA tools and libraries
endef

define Package/srtla/description
	SRTLA utilities for sending and receiving SRT feeds with link aggregation
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
	$(CP) ./src/* $(PKG_BUILD_DIR)/
endef

define Package/quectel-CM-5G/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/srtla_send $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/srtla_rec $(1)/usr/bin
endef

$(eval $(call BuildPackage,srtla))
