# @(#)Makefile	1.4 (PGPMoose) 95/10/11

SCRIPTS = pmapp pmcanon pmcheck pmnewsgroups
DOC	= README pmapp.1 pmcanon.1 pmcheck.1 pmnewsgroups.1 Makefile
DAEMON	= pmdaemon pmcancel pmdaemon.1 pmcancel.1 pmcancel.pgp \
		checkedgroups PGP_Moose_accept

all:
	chmod +x $(SCRIPTS)
	chmod +x pmdaemon pmcancel
	chmod a+r pmcancel.pgp

dist:	all PGPMoose.shar PMDaemon.tar.Z PGPMoose.tar.Z

PGPMoose.shar: $(DOC) $(SCRIPTS)
	shar $(DOC) $(SCRIPTS) >PGPMoose.shar

PMDaemon.tar.Z: $(DAEMON)
	tar -cf - $(DAEMON) | compress >PMDaemon.tar.Z

PGPMoose.tar.Z: PMDaemon.tar.Z PGPMoose.shar
	tar -cf - $(DOC) $(SCRIPTS) $(DAEMON) | compress >PGPMoose.tar.Z
