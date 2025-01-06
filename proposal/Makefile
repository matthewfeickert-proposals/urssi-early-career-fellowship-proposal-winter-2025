FILES=$(wildcard ./cover_letter.tex ./research_proposal_*.tex)
# FILES=$(wildcard ./cover_letter_*.tex)

LATEX = lualatex

all: project_proposal

project_proposal: project_proposal.tex
	latexmk -$(LATEX) -logfilewarnings -halt-on-error $(basename $@)
	rsync $(basename $@).pdf $(basename $@)_feickert.pdf

cleanpartial:
	-@rm *.aux *.bbl *.bcf *.blg *.dvi *.glg *.glo *.gls *.ist *.lof *.log *.lot *.out *.ps *.run.xml *.toc 2>/dev/null || true

clean:
	rm -f *.aux *.bbl *.blg *.dvi *.idx *.lof *.log *.lot *.toc \
		*.glg *.gls *.glo *.xdy *.nav *.out *.snm *.vrb *.mp \
		*.synctex.gz *.brf *.fls *.fdb_latexmk

realclean: clean
	rm -f *.ps *.pdf
	rm -rf submit
