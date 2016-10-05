### -*- mode: makefile-gmake -*-

# Note: If building on Mac OS X, and if you use MacPorts, the following ports
# should be installed:
#
#   texlive-latex
#   texlive-plain-extra
#   texlive-latex-recommended
#   texlive-latex-extra
#   texlive-fonts-recommended
#   texlive-fonts-extra
#   texlive-generic-recommended

FIGURES = $(patsubst %.dot,%.pdf,$(wildcard *.dot))

TSPDF = pdflatex ts | grep -v "^Overfull"

default: rebuild

clean:
	rm -f *.aux *.idx *.ilg *.ind *.log *.lot *.lof *.tmp *.out *.toc ts.pdf

refresh:
	$(TSPDF)

rebuild:
	$(TSPDF)
	$(TSPDF)
	$(TSPDF)

full: $(FIGURES) reindex

%.pdf: %.dot
	dot -o $@ -Tpdf $<

reindex:
	$(TSPDF)
	$(TSPDF)
	$(TSPDF)
	makeindex generalindex
	makeindex libraryindex
	makeindex impldefindex
	$(TSPDF)
	$(TSPDF)

### Makefile ends here
