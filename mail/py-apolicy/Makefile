# Created by: Chifeng QU <chifeng@gmail.com>
# $FreeBSD$

PORTNAME=	apolicy
PORTVERSION=	0.73
PORTREVISION=	2
CATEGORIES=	mail python
MASTER_SITES=	http://download.gna.org/apolicy/%SUBDIR%/ \
		http://www.chifeng.name/dist/apolicy/%SUBDIR%/ \
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	ports@FreeBSD.org
COMMENT=	ACL system for Postfix, as a policy daemon

LICENSE=	GPLv2
LICENSE_FILE=	${WRKSRC}/LICENSE.TXT

RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}ipy>=0:net-mgmt/py-ipy \
		${PYTHON_PKGNAMEPREFIX}pyspf>=0:mail/py-pyspf

USES=		python twisted
USE_PYTHON=	distutils
NO_ARCH=	yes
NO_BUILD=	yes
USE_RC_SUBR=	apolicyd

SUB_LIST=	PYTHON_SITELIBDIR=${PYTHON_SITELIBDIR} \
		PYTHON_CMD=${PYTHON_CMD}
SUB_FILES=	pkg-message

post-patch:
	@${REINPLACE_CMD} 's|/etc|${PREFIX}/etc|' ${WRKSRC}/setup.py

.include <bsd.port.mk>
