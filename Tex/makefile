##
# LaTeX Makefile
##

# Dependencies
BIBLIO   = Bibliography.bib
DEPENDS  = $(BIBLIO)

# EPS figures
FIGURES := $(wildcard figures/*.eps)
FIGURES := $(patsubst %.eps,%.pdf,$(FIGURES))

all: Paper.pdf

Paper.pdf: Paper.tex $(DEPENDS) $(FIGURES)
	# sed -i '/language = /d' $(BIBLIO)
	# sed -i '/abstract = /d' $(BIBLIO)
	# sed -i '/keywords = /d' $(BIBLIO)
	# sed -i '/file = /d' $(BIBLIO)
	latexmk -pdf -pdflatex="pdflatex -interaction=nonstopmode" -use-make Paper.tex
	latexmk -c

%.pdf : %.eps
	epstopdf $<

clean:
	latexmk -CA
	rm PaperNotes.bib
	rm Paper.bbl
