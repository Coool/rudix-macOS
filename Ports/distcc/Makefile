include ../../Library/GNU.mk

Title=		DistCC
Name=		distcc
Version=	3.4
Site=		https://distcc.github.io/
Source=		https://github.com/distcc/distcc/releases/download/v3.4/distcc-$(Version).tar.gz
License=	GPLv2

define test_hook
$(BinDir)/distcc --version | grep $(Version)
endef
