# $FreeBSD$

PORTNAME=	trollius
PORTVERSION=	2.0
CATEGORIES=	devel python
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	skreuzer@FreeBSD.org
COMMENT=	Port of the Tulip project (asyncio module, PEP 3156) on Python 2

LICENSE=	APACHE20
LICENSE_FILE=	${WRKSRC}/COPYING

USES=		python
USE_PYTHON=	autoplist distutils

NO_ARCH=	yes

.include <bsd.port.pre.mk>

.if ${PYTHON_REL} < 3000
RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}futures>0:devel/py-futures
TEST_DEPENDS=	${PYTHON_PKGNAMEPREFIX}unittest2>0:devel/py-unittest2
.if ${PYTHON_REL} < 3300
TEST_DEPENDS+=	${PYTHON_PKGNAMEPREFIX}mock>0:devel/py-mock
.endif
.endif

do-test:
	@cd ${WRKSRC} && \
	${PYTHON_CMD} runtests.py

.include <bsd.port.post.mk>
