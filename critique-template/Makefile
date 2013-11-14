targets=template.pdf

all: $(targets)

%.pdf: %.tex
	latexmk -pdf $^

clean:
	rm -rf *.aux *.dvi *.fdb_latexmk *.fls *.log *.pdf
