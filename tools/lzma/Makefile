# 
# Copyright (C) 2006 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk

PKG_NAME:=lzma
PKG_VERSION:=22.01
PKG_SOURCE_VERSION:=2201

PKG_SOURCE:=$(PKG_NAME)$(PKG_SOURCE_VERSION).7z
PKG_SOURCE_URL:=https://7-zip.org/a/
PKG_HASH:=35b1689169efbc7c3c147387e5495130f371b4bad8ec24f049d28e126d52d9fe

include $(INCLUDE_DIR)/host-build.mk

LZMACON=$(HOST_BUILD_DIR)/CPP/7zip/Bundles/LzmaCon

define Host/Compile
	$(MAKE) -C $(LZMACON) -f makefile.gcc
endef

define Host/Install
	$(INSTALL_BIN) $(LZMACON)/_o/lzma $(STAGING_DIR_HOST)/bin/lzma
endef

define Host/Clean
	rm -f $(STAGING_DIR_HOST)/bin/lzma
endef

$(eval $(call HostBuild))
