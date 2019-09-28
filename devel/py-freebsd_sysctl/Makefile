# $FreeBSD$

PORTNAME=		freebsd_sysctl
PORTVERSION=	0.0.6
CATEGORIES=		devel python
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=		stefan@gronke.net
COMMENT=		Native Python wrapper for FreeBSD jails using libc

LICENSE=		BSD2CLAUSE
LICENSE_FILE=	${WRKSRC}/LICENSE.txt

USES=			python:3.6+

USE_GITHUB=		yes
GH_ACCOUNT=		gronke
GH_PROJECT=		py-freebsd_sysctl

NO_ARCH=		yes
USE_PYTHON=		distutils py3kplist autoplist

PLIST_SUB+=		PORTVERSION=${PORTVERSION}

.include <bsd.port.mk>
