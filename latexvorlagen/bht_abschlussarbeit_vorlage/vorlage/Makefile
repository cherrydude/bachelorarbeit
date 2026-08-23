LATEX=latex
BIBTEX=bibtex
DVIPDF=dvipdf

all: abschlussarbeit


abschlussarbeit:
	$(LATEX) $@ && $(BIBTEX) $@.aux && $(LATEX) $@ && $(LATEX) $@
	$(DVIPDF) -dALLOWPSTRANSPARENCY $@.dvi $@.pdf

pdfclean:
	$(RM) *pdf

clean:
	$(RM) *~ *.aux *.log *.toc *.dvi *.bbl *.lot *.blg *.lof *.out *.lol *.ps
