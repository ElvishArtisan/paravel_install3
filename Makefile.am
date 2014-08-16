## automake.am
##
## Top level automake.am for paravel_install
##
## Use automake to process this into a Makefile.in
##
##   (C) Copyright 2010-14 Fred Gleason <fredg@paravelsystems.com>
##       All Rights Reserved.
##

ACLOCAL_AMFLAGS = -I m4

rpm:	dist
	mkdir -p $(HOME)/rpmbuild/SOURCES
	cp paravel_install3-$(VERSION).tar.gz $(HOME)/rpmbuild/SOURCES/
	$(RPMBUILD) -ba --target $(ARCH)-$(VENDOR)-linux paravel_install3.spec
	mv $(HOME)/rpmbuild/RPMS/$(ARCH)/paravel_install3-*.rpm $(top_srcdir)/
	mv $(HOME)/rpmbuild/SRPMS/paravel_install3-*.src.rpm $(top_srcdir)/
	rm $(HOME)/rpmbuild/SOURCES/paravel_install3-$(VERSION).tar.gz

EXTRA_DIST = asound.conf\
             autogen.sh\
             gpg_keys\
             PACKAGE_VERSION rivendell.sh\
             paravelvnc\
             Paravel-Broadcast.repo\
             paravel_install3.spec.in\
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
