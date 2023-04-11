include $(TOPDIR)/rules.mk

PKG_NAME:=tpm2-tools
PKG_VERSION:=5.5
PKG_RELEASE:=1

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_URL:=https://github.com/tpm2-software/$(PKG_NAME)/releases/download/$(PKG_VERSION)/
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_HASH:=1fdb49c730537bfdaed088884881a61e3bfd121e957ec0bdceeec0261236c123
PKG_FIXUP:=configure
PKG_LICENSE:=BSD-3-Clause
PKG_LICENSE_FILES:=LICENSE
PKG_BUILD_DEPENDS:=tpm2-tss openssl libcurl

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
  SECTION:=utils
  CATEGORY:=Utilities
  SUBMENU:=TPM2
  TITLE:=TPM2-TOOLS
  URL:=https://github.com/tpm2-software/tpm2-tools
  DEPENDS+= +tpm2-tss +libopenssl +libcurl +efivar
endef

TARGET_CFLAGS:= -U_FORTIFY_SOURCE $(TARGET_OPTIMIZATION)$(if $(CONFIG_DEBUG), -g3) $(EXTRA_OPTIMIZATIONS)

define Package/$(PKG_NAME)/description
  TPM (Trusted Platform Module) 2 tools
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/tools/tpm2 $(1)/usr/bin
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
