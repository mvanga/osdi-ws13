MAKE = make

.PHONY: all clean texshop

ALL = main.pdf

all: ${ALL}


TEX  := $(shell find .    -name '*.tex')
PDFS := $(shell find figs -name '*.pdf' | grep -v .graffle)

main.pdf: ${TEX} ${PDFS}
	latexmk -pdf main.tex

%.texshop: Makefile
	@printf  "main.tex" > $@

texshop: $(subst .tex,.texshop, $(TEX))
	@echo Generating .texshop files...


EXTS  = *~ *.aux *.backup *.blg *.log *.out *.lof *.loa *.lot *.toc *.bbl *.bak *.texshop *.dvi *.fdb_latexmk
TRASH := $(foreach ext,${EXTS},$(shell find . -name '${ext}'))

clean:
	@echo Cleaning  ${EXTS} ${ALL}...
	@rm -f ${TRASH} ${ALL}
