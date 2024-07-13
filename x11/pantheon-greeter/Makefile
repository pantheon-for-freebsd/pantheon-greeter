PORTNAME=	pantheon-greeter
DISTVERSION=	7.0.0
CATEGORIES=	x11

MAINTAINER=	inucat@proton.me
COMMENT=	Greeter for Pantheon desktop environment
WWW=		https://github.com/elementary/greeter

LICENSE=	GPLv3

LIB_DEPENDS=\
		libgranite.so:x11-toolkits/granite \
		libhandy-1.so:x11-toolkits/libhandy \
		libaccountsservice.so:sysutils/accountsservice \
		liblightdm-gobject-1.so:x11/lightdm \
		libmutter-10.so:x11-wm/mutter \
		libgee-0.8.so:devel/libgee \
		libgraphene-1.0.so:graphics/graphene

USES=			meson ninja vala gnome gettext
MESON_ARGS=		--prefix=${PREFIX}
MESON_BUILD_DIR=	build
USE_GNOME=		glib20 gtk30
USE_GITHUB=		yes
GH_ACCOUNT=		elementary
GH_PROJECT=		greeter

do-build:
	cd ${WRKSRC} && meson setup build
	cd ${WRKSRC}/build && ninja

do-stage:
	cd ${WRKSRC}/build && DESTDIR=${WRKSRC}/../stage ninja install

.include <bsd.port.mk>
