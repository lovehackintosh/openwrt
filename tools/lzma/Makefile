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

PKG_SOURCE:=$(PKG_NAME)$(PKG_SOURCE_VERSION).tar.xz
PKG_SOURCE_URL:=https://github.com/lovehackintosh/Actions-OpenWrt/raw/update-kernel/
PKG_HASH:=4eac421f429b37ac9ef360a55f47ebabb6a9e8de4502dcc8a2a1f48eb3803ecf

include $(INCLUDE_DIR)/host-build.mk

LZMACON=$(HOST_BUILD_DIR)/CPP/7zip/Bundles/LzmaCon

define Host/Compile
	$(MAKE) $(HOST_JOBS) -C $(LZMACON) -f makefile.gcc
endef

define Host/Install
	$(INSTALL_BIN) $(LZMACON)/_o/lzma $(STAGING_DIR_HOST)/bin/lzma
endef

define Host/Clean
	rm -f $(STAGING_DIR_HOST)/bin/lzma
endef

$(eval $(call HostBuild))
