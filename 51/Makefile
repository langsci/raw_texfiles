# specify your book target here:
all: book pod cover

# specify thh book file and all the files that you are including
SOURCE= $(wildcard *.tex) $(wildcard chapters/*.tex)\
references.bib\
LSP/langsci.cls
	 
book.pdf: $(SOURCE)
	xelatex -no-pdf book 
	bibtex -min-crossrefs=200 book
	xelatex  -no-pdf book
	sed -i s/.*\\emph.*// book.adx #remove titles which biblatex puts into the name index
	makeindex -o book.and book.adx
	makeindex -o book.lnd book.ldx
	makeindex -o book.snd book.sdx
	xelatex -no-pdf book 
	xelatex book 

#create only the book
book: book.pdf 

#create a png of the cover
cover: book.pdf
	convert book.pdf\[0\] -quality 100 -background white -alpha remove -bordercolor black -border 2  cover.png
	display cover.png
	convert -geometry 50x50% cover.png covertwitter.png
 
#prepare for print on demand services	
pod: bod createspace
 

#prepare for submission to BOD
bod: book.pdf  
	sed "s/output=short/output=coverbod/" book.tex >bodcover.tex 
	xelatex bodcover.tex 
	xelatex bodcover.tex
	mv bodcover.pdf bod
	./filluppages 4 book.pdf bod/bodcontent.pdf 

# prepare for submission to createspace
createspace:  book.pdf
	sed "s/output=short/output=covercreatespace/" book.tex >createspacecover.tex 
	xelatex createspacecover.tex
	xelatex createspacecover.tex
	mv createspacecover.pdf createspace
	./filluppages 1 book.pdf createspace/createspacecontent.pdf 

#housekeeping	
clean:
	rm -f *.bak *~ *.backup *.tmp \
	*.adx *.and *.idx *.ind *.ldx *.lnd *.sdx *.snd *.rdx *.rnd *.wdx *.wnd \
	*.log *.blg *.ilg \
	*.aux *.toc *.cut *.out *.tpm *.bbl *-blx.bib *_tmp.bib \
	*.glg *.glo *.gls *.wrd *.wdv *.xdv \
	*.run.xml

realclean: clean
	rm -f *.dvi *.ps *.pdf 
