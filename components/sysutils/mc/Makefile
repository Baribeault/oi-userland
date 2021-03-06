#
# CDDL HEADER START
#
# The contents of this file are subject to the terms of the
# Common Development and Distribution License (the "License").
# You may not use this file except in compliance with the License.
#
# You can obtain a copy of the license at usr/src/OPENSOLARIS.LICENSE
# or http://www.opensolaris.org/os/licensing.
# See the License for the specific language governing permissions
# and limitations under the License.
#
# When distributing Covered Code, include this CDDL HEADER in each
# file and include the License file at usr/src/OPENSOLARIS.LICENSE.
# If applicable, add the following below this CDDL HEADER, with the
# fields enclosed by brackets "[]" replaced with your own identifying
# information: Portions Copyright [yyyy] [name of copyright owner]
#
# CDDL HEADER END
#

#
# Copyright (c) 2011, 2013, Oracle and/or its affiliates. All rights reserved.
# Copyright (c) 2020, Michal Nowak
#

BUILD_BITS=		64

include ../../../make-rules/shared-macros.mk

COMPONENT_NAME=		mc
COMPONENT_VERSION=	4.8.24
COMPONENT_FMRI=		file/mc
COMPONENT_SUMMARY=	The GNU Midnight Commander file manager
COMPONENT_DESCRIPTION=	GNU Midnight Commander is a full-screen text mode application that allows user to copy, move and delete files and whole directory trees, search for files and run commands in the subshell
COMPONENT_CLASSIFICATION=	Desktop (GNOME)/File Managers
COMPONENT_PROJECT_URL=	http://www.midnight-commander.org/
COMPONENT_SRC=		$(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=	$(COMPONENT_SRC).tar.xz
COMPONENT_ARCHIVE_HASH=	\
	sha256:859f1cc070450bf6eb4d319ffcb6a5ac29deb0ac0d81559fb2e71242b1176d46
COMPONENT_ARCHIVE_URL=	http://ftp.midnight-commander.org/$(COMPONENT_ARCHIVE)
COMPONENT_LICENSE=	GPLv3

include $(WS_MAKE_RULES)/common.mk

CONFIGURE_BINDIR.64 = $(CONFIGURE_PREFIX)/bin

CONFIGURE_OPTIONS += --sysconfdir=/usr/share
CONFIGURE_OPTIONS += --libexecdir=/usr/share
CONFIGURE_OPTIONS += --with-samba
CONFIGURE_OPTIONS += --with-x
CONFIGURE_OPTIONS += --enable-charset
CONFIGURE_OPTIONS += --without-ext2undel
CONFIGURE_OPTIONS += --with-screen=slang
CONFIGURE_OPTIONS += --enable-vfs-sftp=no
CONFIGURE_OPTIONS += "mc_cv_nroff_tascii="

COMPONENT_TEST_TRANSFORMS += \
	'-n ' \
	'-e "/TOTAL/p" ' \
	'-e "/SKIP/p" ' \
	'-e "/PASS/p" ' \
	'-e "/FAIL/p" ' \
	'-e "/ERROR/p" '

REQUIRED_PACKAGES += runtime/perl-522
# Auto-generated dependencies
REQUIRED_PACKAGES += library/glib2
REQUIRED_PACKAGES += library/slang
REQUIRED_PACKAGES += runtime/perl-524
REQUIRED_PACKAGES += SUNWcs
REQUIRED_PACKAGES += system/library
