# $NetBSD: Makefile,v 1.58 2021/04/21 11:40:50 adam Exp $

DISTNAME=	qtdeclarative-everywhere-src-${QTVERSION}
PKGNAME=	qt5-qtdeclarative-${QTVERSION}
PKGREVISION=	3
COMMENT=	Qt5 module for declarative framework

BUILD_TARGET=		sub-tools
INSTALL_ENV+=		INSTALL_ROOT=${DESTDIR}
INSTALLATION_DIRS+=	lib/pkgconfig
PYTHON_FOR_BUILD_ONLY=	tool

.include "../../x11/qt5-qtbase/Makefile.common"

post-install:
.for i in Qt5Qml.pc Qt5Quick.pc Qt5QuickTest.pc Qt5QuickWidgets.pc
	cd ${DESTDIR}${PREFIX}/lib/pkgconfig && \
	${LN} -f -s ${QTPREFIX}/lib/pkgconfig/${i} ${i}
.endfor

.include "../../x11/qt5-qtbase/buildlink3.mk"
.include "../../lang/python/tool.mk"
.include "../../mk/bsd.pkg.mk"
