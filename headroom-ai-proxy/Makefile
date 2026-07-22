PORTNAME=		headroom-ai-proxy
DISTVERSION=		0.31.0.20260714
CATEGORIES=		misc

MAINTAINER=		pr9000@tutamail.com
COMMENT=		Headroom transparent reverse proxy
WWW=			https://github.com/headroomlabs-ai/headroom

LICENSE=		APACHE20


USES=			cargo perl5
USE_PERL5=		build
BUILD_DEPENDS=		cmake:devel/cmake-core

USE_GITHUB=		yes
GH_TUPLE=		PR9000:headroom:315b9f687a0c35a973080f01539d128ed09099b4:DEFAULT \
			pykeio:ort:6be513209d40e58ffeebdaaf46cba37d3e967b1e:ort


CARGO_INSTALL_PATH=	crates/headroom-proxy

PLIST_FILES=		bin/headroom-ai-proxy

post-extract:
	@${CP} ${FILESDIR}/Cargo.lock ${WRKSRC}/Cargo.lock

post-install:
	${MV} ${STAGEDIR}${PREFIX}/bin/headroom-proxy \
		${STAGEDIR}${PREFIX}/bin/headroom-ai-proxy

.include <bsd.port.mk>
