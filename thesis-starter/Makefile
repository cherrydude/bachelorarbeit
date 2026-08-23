TARGET=main
PDFLATEX=pdflatex
BIBTEX=bibtex

.PHONY: all clean pdfclean

all: $(TARGET).pdf

$(TARGET).pdf: $(TARGET).tex
	$(PDFLATEX) $(TARGET)
	$(BIBTEX) $(TARGET)
	$(PDFLATEX) $(TARGET)
	$(PDFLATEX) $(TARGET)

clean:
	rm -f *.aux *.bbl *.bcf *.blg *.fdb_latexmk *.fls *.lof *.log *.lot *.out *.run.xml *.toc

pdfclean:
	rm -f $(TARGET).pdf
