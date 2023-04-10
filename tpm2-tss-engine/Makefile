include $(TOPDIR)/rules.mk

PKG_NAME:=tpm2-tss-engine
PKG_VERSION:=1.2.0
PKG_RELEASE:=1

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_URL:=https://github.com/tpm2-software/tpm2-tss-engine.git
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_HASH:=3c94fef110dd3630b3c28c5875febba76b7d5ba2fcc04a14c4a30f5d2157c265
PKG_FIXUP:=autoreconf
PKG_LICENSE:=BSD-2
PKG_LICENSE_FILES:=LICENSE
PKG_BUILD_DEPENDS:=openssl libtool m4 ruby


PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/nls.mk

define Package/$(PKG_NAME)
  SECTION:=utils
  CATEGORY:=Utilities
  SUBMENU:=TPM2
  TITLE:=TPM2-TSS-ENGINE
  URL:=http://trousers.sourceforge.net
  DEPENDS+= +libopenssl
endef

#TARGET_CFLAGS:= -U_FORTIFY_SOURCE $(TARGET_OPTIMIZATION)$(if $(CONFIG_DEBUG), -g3) $(EXTRA_OPTIMIZATION)

define Package/$(PKG_NAME)/description
TPM2-TSS-ENGINE
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/bin
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
