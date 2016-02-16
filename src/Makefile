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

full: $(FIGURES) grammar xrefs reindex

%.pdf: %.dot
	dot -o $@ -Tpdf $<

grammar:
	sh ../tools/makegram

xrefs:
	sh ../tools/makexref

# reindex:
# 	$(TSPDF)
# 	$(TSPDF)
# 	$(TSPDF)
# 	makeindex generalindex
# 	makeindex libraryindex
# 	makeindex grammarindex
# 	makeindex impldefindex
# 	$(TSPDF)
# 	$(TSPDF)

### Makefile ends here
