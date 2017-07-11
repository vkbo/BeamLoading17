##
# LaTeX Makefile
##

# Dependencies
BIBLIO  = Bibliography.bib
DEPENDS = $(BIBLIO)

# Figures
FIGEPS := $(wildcard figures/*.eps)
FIGSVG := $(wildcard figures/*.svg)
FIGEPS := $(patsubst %.eps,%.pdf,$(FIGEPS))
FIGSVG := $(patsubst %.svg,%.pdf,$(FIGSVG))

all: Paper.pdf

Paper.pdf: Paper.tex $(DEPENDS) $(FIGEPS) $(FIGSVG)
	latexmk -pdf -pdflatex="pdflatex -interaction=nonstopmode" -use-make Paper.tex
	latexmk -c

%.pdf : %.eps
	epstopdf $<

%.pdf : %.svg
	inkscape -f $< -A $@

clean:
	latexmk -CA
	rm PaperNotes.bib
	rm Paper.bbl
