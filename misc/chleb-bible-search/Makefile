PORTNAME=	chleb-bible-search
DISTVERSION=	0.11.0
CATEGORIES=	misc perl5
DISTVERSIONPREFIX=v
USE_GITHUB=     yes
GH_ACCOUNT=     daybologic
MAINTAINER=	2e0eol@gmail.com
COMMENT=	Chleb Bible Search
WWW=		https://github.com/daybologic/chleb-bible-search
USES=		perl5 shebangfix
USE_PERL5=	configure build run
PORTREVISION=	2
LICENSE=	BSD3CLAUSE
NO_ARCH=	yes
MAKE_JOBS_UNSAFE=yes

PATCHFILES=\
	chleb-bible-search-0.11.0.container.patch

post-install:
	${MKDIR} ${STAGEDIR}/var/log/${PORTNAME}
	${MKDIR} ${STAGEDIR}${PREFIX}/etc/${PORTNAME}
	${CP} ${WRKDIR}/${PORTNAME}-${DISTVERSION}/etc/log4perl.conf ${STAGEDIR}${PREFIX}/etc/${PORTNAME}/log4perl.conf.sample
	${CP} ${WRKDIR}/${PORTNAME}-${DISTVERSION}/etc/main.conf ${STAGEDIR}${PREFIX}/etc/${PORTNAME}/main.conf.sample

MY_DEPENDS=\
	p5-Config-INI>0:devel/p5-Config-INI \
	p5-Dancer2>0:www/p5-Dancer2 \
	p5-DateTime>0:devel/p5-DateTime \
	p5-DateTime-Format-Strptime>0:devel/p5-DateTime-Format-Strptime \
	p5-Digest-CRC>0:security/p5-Digest-CRC \
	p5-JSON>0:converters/p5-JSON \
	p5-Log-Log4perl>0:devel/p5-Log-Log4perl \
	p5-Moose>0:devel/p5-Moose \
	p5-MooseX-Singleton>0:devel/p5-MooseX-Singleton \
	p5-Readonly>0:devel/p5-Readonly \
	p5-Time-Duration>0:devel/p5-Time-Duration \
	p5-UUID-Tiny>0:devel/p5-UUID-Tiny

BUILD_DEPENDS=	${MY_DEPENDS}
RUN_DEPENDS=	${MY_DEPENDS}

TEST_DEPENDS=\
	${MY_DEPENDS} \
	p5-Log-Log4perl>0:devel/p5-Log-Log4perl \
	p5-Test-Deep>0:devel/p5-Test-Deep \
	p5-Test-Exception>0:devel/p5-Test-Exception \
	p5-Test-Module-Runnable>0:devel/p5-Test-Module-Runnable

.include <bsd.port.pre.mk>

.if ${PERL_LEVEL} < 5
TEST_DEPENDS+=	p5-Module-CoreList>0:devel/p5-Module-CoreList
.endif

.include <bsd.port.post.mk>
