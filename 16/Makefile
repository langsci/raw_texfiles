# specify your main target here:
all: cangemi.pdf

# specify the main file and all the files that you are including
SOURCE= cangemi.tex chapters/chapter1.tex chapters/chapter2.tex chapters/chapter3.tex chapters/chapter4.tex chapters/chapter5.tex chapters/chapter6.tex\
biblio.bib\
LSP/langsci.cls


	 
%.pdf: %.tex $(SOURCE)
	xelatex -no-pdf cangemi 
#	bibtex -min-crossrefs=200 cangemi
	xelatex  -no-pdf cangemi
	makeindex -o cangemi.ind cangemi.idx
	makeindex -o cangemi.lnd cangemi.ldx
#	makeindex -o cangemi.wnd cangemi.wdx
#	LSP/bin/reverse-index <cangemi.wdx >cangemi.rdx
#	makeindex -o cangemi.rnd cangemi.rdx 
	authorindex -i -p cangemi.aux > cangemi.bib.adx
	sed 's/|hyperpage//' cangemi.adx > cangemi.txt.adx 
	cat cangemi.bib.adx cangemi.txt.adx > cangemi.combined.adx
	sed -e 's/}{/|hyperpage}{/g' cangemi.combined.adx > cangemi.combined.adx.hyp
	makeindex -o cangemi.and cangemi.combined.adx.hyp
	xelatex -no-pdf cangemi 
	xelatex cangemi 


cover: cangemi.pdf
	convert cangemi.pdf\[0\] -resize 486x -background white -alpha remove -bordercolor black -border 2  cover.png

clean:
	rm -f *.bak *~ *.log *.blg *.aux *.toc *.cut *.out *.tmp *.tpm *.adx *.adx.hyp *.idx *.ilg \
	*.and *.glg *.glo *.gls *.wdx *.wnd *.wrd *.wdv *.ldx *.lnd *.rdx *.rnd *.xdv 

realclean: clean
	rm -f *.dvi *.ps *.pdf *.bbl
