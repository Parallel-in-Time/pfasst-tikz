EXAMPLES=pfasst manysteps predictstep fullpredict manualpredict beamer ghost
EXAMPLES_PDF:=$(addsuffix .pdf, ${EXAMPLES})
EXAMPLES_SVG:=$(addsuffix .svg, ${EXAMPLES})

all: ${EXAMPLES_PDF}
svg: ${EXAMPLES_SVG}
%.pdf: %.tex ../pfasst-tikz.tex
	latexmk -pdf $<
	pdfcrop --hires $@ $@
%.svg: %.pdf
	pdf2svg $< $@

.PHONY: clean
clean:
	rm -f *.aux *.log *.pdf *.svg *.fdb_latexmk *.fls *.out *.nav *.toc *.snm
