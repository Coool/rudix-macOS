BuildRequires += $(BinDir)/autoconf	# autoconf
BuildRequires += $(BinDir)/automake	# automake
BuildRequires += $(BinDir)/pkg-config	# pkg-config

include ../../Library/GNU.mk

Title=		Exuberant Ctags
Name=		ctags
Version=	5.9
Site=		https://ctags.io/
Source=		https://github.com/universal-ctags/ctags/archive/refs/tags/p$(Version).20211031.0.tar.gz
License=	GPLv2+

UncompressedName=ctags-p$(Version).20211031.0

GnuConfigureExtra = --enable-etags
MakeInstallExtra += prefix=$(DestDir)/$(Prefix)
MakeInstallExtra += mandir=$(DestDir)/$(ManDir)

define build_hook
cd $(BuildDir) && ./autogen.sh && env $(EnvExtra) $(gnu_configure) && $(make) $(MakeExtra)
endef

define after_install_hook
install	-m 644 $(SourceDir)/{FAQ,*.html} $(DestDir)/$(DocDir)/$(Name)
cd $(DestDir)/$(BinDir) ; ln -sf ctags exuberant-ctags ; ln -sf etags exuberant-etags
cd $(DestDir)/$(ManDir)/man1 ; ln -sf ctags.1 exuberant-ctags.1 ; ln -sf etags.1 exuberant-etags.1
endef

define test_hook
$(BinDir)/ctags --version | grep $(Version)
endef
