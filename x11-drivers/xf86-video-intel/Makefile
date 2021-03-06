# Created by: lesi@FreeBSD.org
# $FreeBSD$

PORTNAME=	xf86-video-intel
PORTVERSION=	2.21.15
PORTREVISION=	9
CATEGORIES=	x11-drivers

MAINTAINER=	x11@FreeBSD.org
COMMENT=	Driver for Intel integrated graphics chipsets

LIB_DEPENDS=	libxcb-util.so:x11/xcb-util

ONLY_FOR_ARCHS=	amd64 i386
USE_GL=		gl

USE_LDCONFIG=	yes
XORG_CAT=	driver
USE_XORG=	glproto \
		pixman \
		x11 \
		xext \
		xf86driproto \
		xineramaproto \
		xrender \
		xvmc

USES+=		cpe
CPE_VENDOR=	x

CONFIGURE_ENV+=	xorg_cv_cc_flag__Wno_maybe_uninitialized=no
CONFIGURE_ARGS+=	--enable-sna
CONFIGURE_ARGS+=	--disable-glamor
INSTALL_TARGET=	install-strip

.include <bsd.port.options.mk>

.if (${OSVERSION} >= 903000 && ${OSVERSION} < 1000000)
RUN_DEPENDS+=	drm-kmod>=9:x11-drivers/drm-kmod

post-patch:
	@${REINPLACE_CMD} -e 's|"i915kms"|"i915kms_port"|g' \
		${WRKSRC}/src/intel_device.c
.endif

.include <bsd.port.mk>
