# $NetBSD: Makefile,v 1.25 2021/05/24 19:53:24 wiz Exp $
#

DISTNAME=		IP-Country-2.28
PKGNAME=		p5-${DISTNAME}
PKGREVISION=		7
CATEGORIES=		net perl5
MASTER_SITES=		${MASTER_SITE_PERL_CPAN:=IP/}

MAINTAINER=		pkgsrc-users@NetBSD.org
HOMEPAGE=		https://metacpan.org/release/IP-Country
COMMENT=		Fast lookup of country codes from IP addresses
#LICENSE=		${PERL5_LICENSE}
# See COPYRIGHT part of lib/IP/Country.pm (Re: RIPE database)

DEPENDS+=		p5-Geography-Countries-[0-9]*:../../geography/p5-Geography-Countries

USE_LANGUAGES=		# empty
PERL5_PACKLIST=		auto/IP/Country/.packlist

.include "../../lang/perl5/module.mk"
.include "../../mk/bsd.pkg.mk"
