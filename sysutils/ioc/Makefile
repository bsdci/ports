# $FreeBSD$

PORTNAME=	ioc
PORTVERSION=	0.5.0
CATEGORIES=	sysutils

MAINTAINER=	stefan@gronke.net
COMMENT=	Jail management CLI using libioc

LICENSE=	BSD2CLAUSE
LICENSE_FILE=	${WRKSRC}/LICENSE.txt

RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}libioc>0:devel/py-libioc@${PY_FLAVOR} \
				${PYTHON_PKGNAMEPREFIX}texttable>0:textproc/py-texttable@${PY_FLAVOR} \
				${PYTHON_PKGNAMEPREFIX}click>0:devel/py-click@${PY_FLAVOR} \

USE_GITHUB=	yes
GH_ACCOUNT=	bsdci
GH_PROJECT=	ioc

NO_ARCH=	yes
NO_BUILD=   yes
USES=		python:3.6+

post-patch:
	@${REINPLACE_CMD} -e "s#LIB_DIR =.*#LIB_DIR = \"${STAGEDIR}${PREFIX}/lib/ioc\"#" ${WRKSRC}/bin/ioc

pre-install:
	@${MKDIR} ${STAGEDIR}${PREFIX}/lib/ioc

do-install:
	${INSTALL_SCRIPT} ${WRKSRC}/rc.d/ioc ${STAGEDIR}${PREFIX}/etc/rc.d
	${INSTALL_SCRIPT} ${WRKSRC}/bin/ioc ${STAGEDIR}${PREFIX}/bin
	(cd ${WRKSRC}/ && ${COPYTREE_SHARE} ioc_cli ${STAGEDIR}${PREFIX}/lib/ioc)


.include <bsd.port.mk>
