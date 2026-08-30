LATEX=pdflatex
BIBTEX=bibtex
RM=rm -f

.PHONY: build clean all

all: build

build:
	$(LATEX) main.tex && $(BIBTEX) main.aux && $(LATEX) main.tex && $(LATEX) main.tex

clean:
	$(RM) *~ *.aux *.log *.toc *.dvi *.bbl *.lot *.blg *.lof *.out *.lol *.ps *.pdf *.fls *.fdb_latexmk main.run.xml
