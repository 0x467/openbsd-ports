COMMENT=		used by JetBrains IDE's for detecting file changes

V=				20200601
DISTNAME=		fd90ef130f6ccb201a054ef6afee09f3f5f17f18
PKGNAME=		fsnotifier-${V}
CATEGORIES=		devel
REVISION=		0

HOMEPAGE=		https://codeberg.org/0x467/fsnotifier
DISTFILES=		${DISTNAME}${EXTRACT_SUFX}

MAINTAINER=		0x467 <0x467@pm.me>

# Apache 2.0
PERMIT_PACKAGE=	Yes

MASTER_SITES=	${HOMEPAGE}/archive/

LIB_DEPENDS =	devel/libinotify

NO_TEST=		Yes

WRKDIST=	${WRKDIR}/fsnotifier

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/fsnotifier ${PREFIX}/bin

.include <bsd.port.mk>
