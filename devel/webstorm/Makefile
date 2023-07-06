COMMENT=		JavaScript IDE based on IntelliJ IDEA

V=			2023.1.3
DISTNAME=		WebStorm-${V}
PKGNAME=		webstorm-${V}
CATEGORIES=		devel
REVISION=		0

HOMEPAGE=		https://www.jetbrains.com/webstorm/
DISTFILES=		${DISTNAME}${EXTRACT_SUFX}

MAINTAINER =		0x467 <0x467@pm.me>

PERMIT_PACKAGE=	Yes

MASTER_SITES=		https://download.jetbrains.com/webstorm/

MODULES=		java
MODJAVA_VER=		17

BUILD_DEPENDS=		${MODJAVA_RUN_DEPENDS}

RUN_DEPENDS=		devel/desktop-file-utils \
			java/javaPathHelper

NO_TEST=		Yes

WRKDIST=	${WRKDIR}/WebStorm-231.9161.29
WS=			${PREFIX}/webstorm

# If NO_BUILD is set, JAVA_HOME doesn't get defined. So do
# a no-op for do-build.
do-build:
	@true

do-install:
	${INSTALL_DATA_DIR} ${WS}
	@cd ${WRKDIST} && pax -rw . ${WS}
	@rm -rf ${WS}/jbr
	@rm -rf ${WS}/lib/pty4j-native
.for PLUGIN in darwin-x86-64 darwin-aarch64 win32-x86-64
	@rm -rf ${WS}/plugins/cwm-plugin/quiche-native/${PLUGIN}
.endfor
	${INSTALL_DATA_DIR} ${PREFIX}/share/applications
.for PROG in webstorm webstorm-lightedit
	@${SUBST_PROGRAM} ${FILESDIR}/${PROG} ${PREFIX}/bin/${PROG}
	@${SUBST_DATA} ${FILESDIR}/${PROG}.desktop \
		${PREFIX}/share/applications/${PROG}.desktop
.endfor
	${INSTALL_MAN} ${FILESDIR}/webstorm.1 ${PREFIX}/man/man1

.include <bsd.port.mk>
