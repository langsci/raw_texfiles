# specify your main target here:
all: enfield.pdf

# specify teh main file and all the files that you are including
SOURCE= enfield.tex \
localbibliography.bib\
LSP/langsci.cls
	 
%.pdf: %.tex $(SOURCE)
	xelatex -no-pdf enfield 
	bibtex -min-crossrefs=200 enfield
	xelatex  -no-pdf enfield
	makeindex -o enfield.ind enfield.idx
	makeindex -o enfield.lnd enfield.ldx
	makeindex -o enfield.snd enfield.sdx
#	makeindex -o enfield.wnd enfield.wdx
#	LSP/bin/reverse-index <enfield.wdx >enfield.rdx
#	makeindex -o enfield.rnd enfield.rdx 
# 	authorindex -i -p enfield.aux > enfield.bib.adx
# 	sed 's/|hyperpage//' enfield.adx > enfield.txt.adx 
# 	cat enfield.bib.adx enfield.txt.adx > enfield.combined.adx
# 	sed -e 's/}{/|hyperpage}{/g' enfield.adx > enfield.adx.hyp
# 	makeindex -o enfield.and enfield.combined.adx
	xelatex -no-pdf enfield 
	xelatex enfield 


cover: enfield.pdf
	convert enfield.pdf\[0\] -resize 486x -background white -alpha remove -bordercolor black -border 2  cover.png

clean:
	rm -f *.bak *~ *.log *.blg *.aux *.toc *.cut *.out *.tmp *.tpm *.adx *.adx.hyp *.idx *.ilg \
	*.and *.glg *.glo *.gls *.wdx *.wnd *.wrd *.wdv *.ldx *.lnd *.rdx *.rnd *.xdv *.backup *.bbl *.ind 

realclean: clean
	rm -f *.dvi *.ps *.pdf *.bbl
