# $NetBSD: Makefile,v 1.45 2021/02/10 09:48:57 nia Exp $

DISTNAME=		cdk-5.0-20210109
PKGNAME=		${DISTNAME:S/5.0-/5.0./}
CATEGORIES=		devel
MASTER_SITES=		https://invisible-mirror.net/archives/cdk/
EXTRACT_SUFX=		.tgz

MAINTAINER=		pkgsrc-users@NetBSD.org
HOMEPAGE=		https://invisible-island.net/cdk/
COMMENT=		Curses Development Kit
LICENSE=		original-bsd

WRKSRC=			${WRKDIR}/${DISTNAME}
USE_NCURSES=		yes # uses ncurses internals
GNU_CONFIGURE=		yes
USE_LIBTOOL=		yes
USE_TOOLS+=		pkg-config

BUILD_TARGET=		default

INSTALL_MAKE_FLAGS+=	INSTALL_DIR=${DESTDIR}${PREFIX} \
			MAN_DIR=${DESTDIR}${PREFIX}/${PKGMANDIR}/man3
INSTALLATION_DIRS=	share/examples/cdk

# put Cdk's include-directory at the front to avoid conflict with menu.h
CFLAGS+=		-I./include

post-install:
	for file in ${WRKSRC}/examples/*.c ${WRKSRC}/examples/Makefile; do \
		${INSTALL_DATA} $${file} ${DESTDIR}${PREFIX}/share/examples/cdk/; \
	done

.include "../../devel/ncurses/buildlink3.mk"
.include "../../mk/bsd.pkg.mk"
