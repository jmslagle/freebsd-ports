# Created by: Yuri Victorovich <yuri@rawbw.com>
# $FreeBSD$

PORTNAME=	pystun
PORTVERSION=	0.1.0
PORTREVISION=	1
CATEGORIES=	net python
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	yuri@rawbw.com
COMMENT=	Python STUN client for getting NAT type and external IP

LICENSE=	MIT

USES=		python
USE_PYTHON=	autoplist distutils
NO_ARCH=	yes

post-extract:
	@${RM} -rf ${WRKSRC}/tests

.include <bsd.port.mk>
