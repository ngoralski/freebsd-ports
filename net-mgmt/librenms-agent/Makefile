# Created by: Nicolas Goralski <nicolas@goralski.fr>
# $FreeBSD: $

PORTNAME=	librenms-agent
PORTVERSION=	0.1
#PORTREVISION=	1
CATEGORIES=	net-mgmt
MASTER_SITES=	http://git.mathias-kettner.de/git/?p=check_mk.git;a=blob_plain;f=agents/check_mk_agent.freebsd;hb=refs/heads/1.2.8

MAINTAINER=	nicolas@goralski.fr
COMMENT=	librenms agents for monitoring system

LICENSE=	GPLv3

USE_GITHUB=	yes
GH_ACCOUNT=	librenms
GH_PROJECT= librenms-agent
GH_TAGNAME=	21817b6b36692bdca8fac8f3ee4a0258a2d2bcee

USES=		shebangfix
SHEBANG_FILES=	check_mk_agent

NO_BUILD=	yes

RUN_DEPENDS+=	xinetd:security/xinetd \
		bash:shells/bash

LIB_DEPENDS+=	libstatgrab.so:devel/libstatgrab \

# http://git.mathias-kettner.de/git/?p=check_mk.git;a=blob_plain;f=agents/check_mk_agent.freebsd;hb=refs/heads/1.2.8

.include <bsd.port.mk>
