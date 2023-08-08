include $(TOPDIR)/rules.mk

PKG_NAME:=gnulib
PKG_CPE_ID:=cpe:/a:gnu:$(PKG_NAME)
PKG_VERSION:=6a9554a6f27d0aa96a434644752759340695fa5b

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://git.savannah.gnu.org/cgit/$(PKG_NAME).git/snapshot
PKG_HASH:=skip

include $(INCLUDE_DIR)/host-build.mk

define Host/Configure
endef

define Host/Install
	$(INSTALL_DIR) $(1)/share/aclocal
	$(INSTALL_DATA) $(HOST_BUILD_DIR)/m4/*.m4 $(1)/share/aclocal/
	$(INSTALL_DIR) $(1)/share/gnulib
	$(CP) $(HOST_BUILD_DIR)/* $(1)/share/gnulib/
endef

define Host/Clean
	rm -rf $(STAGING_DIR_HOST)/share/gnulib
endef

$(eval $(call HostBuild))
