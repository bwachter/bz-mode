ALL: bz-autoloads.el

.PHONY: clean

SOURCES = bz.el
SOURCES = bz-auth.el bz-bug-mode.el bz-comment-mode.el
SOURCES += bz-list-mode.el bz-rpc.el bz-search.el
SOURCES += bz-search-common.el bz-common-functions.el
SOURCES += bz-rpc-bz.el bz-rpc-rally.el
SOURCES += bz-search-rally.el bz-search-bz.el
SOURCES += bz-bug-mode-bz.el bz-bug-mode-rally.el
ELC = $(SOURCES:.el=.elc)

%.elc: %.el
	emacs -batch -Q -L . -f batch-byte-compile $<

compile: $(ELC)

clean:
	@$(RM) *.elc
	@$(RM) bz-autoloads.el

bz-autoloads.el: $(SOURCES)
	emacs -batch -Q -L . -eval "(progn\
	(let ((generated-autoload-file \"$(CURDIR)/bz-autoloads.el\")\
	      (make-backup-files nil))\
	  (update-directory-autoloads \".\")))"