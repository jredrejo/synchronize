EXTRA_DIST = $(PACKAGE)

all:
	@echo "Compiling $(PACKAGE) project..."
	@(cd $(srcdir)/src/$(PACKAGE); \
	$(GAMBAS_path)/gbc2 -ag; \
	$(GAMBAS_path)/gba2)

install-exec-local:
	@(echo "Installing desktop autostart file"; \
	 mkdir -p $(DESTDIR)/etc/xdg/autostart; \
	 cp synchronize.desktop $(DESTDIR)/etc/xdg/autostart/synchronize.desktop; \
	 cd $(srcdir)/src/$(PACKAGE); \
	 echo "Installing $(PACKAGE).gambas file in $(bindir)..."; \
	 cp $(PACKAGE).gambas $(DESTDIR)/$(bindir) )

uninstall-local:
	 echo "Removing $(PACKAGE).gambas file..."; \
	 rm -f $(DESTDIR)/$(bindir)/$(PACKAGE).gambas; \
	 echo "Removing autostart desktop file..."; \
	 rm -f $(DESTDIR)/etc/xdg/autostart/synchronize.desktop; 

dist-hook:
	@(cd $(distdir)/src/$(PACKAGE); \
	rm -rf `find . -name ".gambas" -o -name ".lock" -o -name ".xvpics" -o -name "*~" -o -name "*.out"  -o -name "*.pot" -o -name "*.gambas" -o -name "core.*" -o -name ".kdbg*"`;)

clean-local:
	@(cd src; \
	rm -rf `find . -name ".gambas" -o -name ".lock" -o -name ".xvpics" -o -name "*~" -o -name "*.out"  -o -name "*.pot" -o -name "*.gambas" -o -name "core.*" -o -name ".kdbg*" -o -name ".svn"`;)



#CLEANFILES =*.gambas *~ *.lock *.xvpics *.out *.pot core.* .kdbg* .svn
#SUBDIRS = src/synchronize
#MAINTAINERCLEANFILES = Makefile.in


