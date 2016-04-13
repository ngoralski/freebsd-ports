# Created by: Nicolas Goralski <nicolas@goralski.fr>
# $FreeBSD: $

PORTNAME=	librenms-agent
PORTVERSION=	0.1
#PORTREVISION=	1
CATEGORIES=	net-mgmt

MAINTAINER=	nicolas@goralski.fr
COMMENT=	librenms agents and plugins for freebsd system

NO_ARCH=	yes
LICENSE=	GPLv3

USE_GITHUB=	yes
GH_ACCOUNT=	ngoralski
GH_PROJECT= librenms-agent-freebsd
GH_TAGNAME=	7d716c9429e3463068c44af8e0bb2293ed6f3402


NO_BUILD=	yes

RUN_DEPENDS+=	xinetd:security/xinetd \
		bash:shells/bash

LIB_DEPENDS+=	libstatgrab.so:devel/libstatgrab \


do-install:
	cd ${STAGEDIR} ; \
	${MKDIR} usr/local/etc/xinet.d/ usr/local/libexec/check_mk_agent/plugins usr/local/libexec/check_mk_agent/repo usr/local/libexec/check_mk_agent/local ; \
	cd ${WRKSRC} ; \
	cp check_mk_agent ${STAGEDIR}/usr/local/bin ; \
	cp check_mk_xinetd ${STAGEDIR}/usr/local/etc/xinet.d/check_mk ; \
	cp snmp/distro ${STAGEDIR}/usr/local/bin ; \
	for agent_local in $$( ${FIND} ./agent-local -type f ! -name README ); do \
		cp "$$agent_local" ${STAGEDIR}/usr/local/libexec/check_mk_agent/repo ; \
	done

.include <bsd.port.mk>
