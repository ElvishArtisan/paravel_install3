## automake.am
##
## Top level automake.am for paravel_install
##
## Use automake to process this into a Makefile.in
##
##   (C) Copyright 2010 Fred Gleason <fredg@paravelsystems.com>
##       All Rights Reserved.
##
##      $Id: Makefile.am,v 1.3 2013/11/19 23:04:47 cvs Exp $
##

ACLOCAL_AMFLAGS = -I m4

rpm:	dist
	cp paravel_install-$(VERSION).tar.gz $(RPM_ROOT)/SOURCES/
	$(RPMBUILD) -ba --target noarch-$(VENDOR)-linux paravel_install.spec
	mv $(RPM_ROOT)/RPMS/noarch/paravel_install-$(VERSION)-@RPM_RELEASE@.noarch.rpm $(top_srcdir)/
	mv $(RPM_ROOT)/SRPMS/paravel_install-$(VERSION)-@RPM_RELEASE@.src.rpm $(top_srcdir)/
	rm $(RPM_ROOT)/SOURCES/paravel_install-$(VERSION).tar.gz
	rm -rf $(RPM_ROOT)/BUILD/paravel_install-$(VERSION)

slack:	all
	./make_slack

EXTRA_DIST = asound.conf\
             autogen.sh\
             gpg_keys\
             PACKAGE_VERSION rivendell.sh\
             paravelvnc\
             Paravel-Broadcast.repo\
             paravel_install.spec.in\
             Reyware.repo\
             RPM-GPG-KEY-Paravel-Broadcast\
             RPM-GPG-KEY-Reyware\
             smb.conf

CLEANFILES = *~ *.tar.gz *.tgz *.mo *.rpm *.zip

DISTCLEANFILES = *.spec\
                 config.guess\
                 config.sub\
                 make_slack

MAINTAINERCLEANFILES = *~ Makefile.in configure aclocal.m4 *.tar.gz\
                       config.guess config.status config.sub install-sh\
                       libtool ltmain.sh missing mkinstalldirs depcomp\
                       *.spec
