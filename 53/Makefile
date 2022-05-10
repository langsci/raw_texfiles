# specify thh main file and all the files that you are including
SOURCE=  book.tex $(wildcard local*.tex) $(wildcard chapters/*.tex) \
langsci/langscibook.cls

# specify your main target here:
pdf: book.bbl book.pdf  #by the time book.pdf, bib assures there is a newer aux file

all: pod cover

complete: index book.pdf

index:  book.snd
 
book.pdf: book.aux
	xelatex book 

book.aux: $(SOURCE)
	xelatex -no-pdf book 

#create only the book
book.bbl:  $(SOURCE) localbibliography.bib  
	xelatex -no-pdf book 
	bibtex -min-crossrefs=200 book 


book.snd: book.bbl
	sed -i s/.*\\emph.*// book.adx #remove titles which biblatex puts into the name index
	sed -i 's/hyperindexformat{\\\(infn {[0-9]*\)}/\1/' book.sdx # ordering of references to footnotes
	sed -i 's/hyperindexformat{\\\(infn {[0-9]*\)}/\1/' book.adx
	sed -i 's/hyperindexformat{\\\(infn {[0-9]*\)}/\1/' book.ldx
# 	python3 fixindex.py
# 	mv mainmod.adx book.adx
	makeindex -o book.and book.adx
	makeindex -o book.lnd book.ldx
	makeindex -o book.snd book.sdx 
	xelatex book 
 

#create a png of the cover
cover: FORCE
	convert book.pdf\[0\] -quality 100 -background white -alpha remove -bordercolor black -border 2  cover.png
	cp cover.png googlebooks_frontcover.png
	convert -geometry 50x50% cover.png covertwitter.png
	display cover.png
 
	
#prepare for print on demand services	
pod: bod createspace googlebooks
 
#prepare for submission to BOD
bod: bod/bodcontent.pdf 

bod/bodcontent.pdf: complete
	sed "s/output=short/output=coverbod/" book.tex >bodcover.tex 
	xelatex bodcover.tex  
	xelatex bodcover.tex  
	mv bodcover.pdf bod
	./filluppages 4 book.pdf bod/bodcontent.pdf 

# prepare for submission to createspace
createspace:  createspace/createspacecontent.pdf 

createspace/createspacecontent.pdf: complete
	sed "s/output=short/output=covercreatespace/" book.tex >createspacecover.tex 
	xelatex createspacecover.tex 
	xelatex createspacecover.tex 
	mv createspacecover.pdf createspace
	./filluppages 1 book.pdf createspace/createspacecontent.pdf 

googlebooks: googlebooks_interior.pdf

googlebooks_interior.pdf: complete
	cp book.pdf googlebooks_interior.pdf
	pdftk book.pdf cat 1 output googlebooks_frontcover.pdf 

openreview: openreview.pdf
	

openreview.pdf: book.pdf
	pdftk book.pdf multistamp orstamp.pdf output openreview.pdf 

proofreading: proofreading.pdf
	

proofreading.pdf: book.pdf
	pdftk book.pdf multistamp prstamp.pdf output proofreading.pdf 

blurb: blurb.html blurb.tex biosketch.tex biosketch.html


blurb.tex: blurb.md
	pandoc -f markdown -t latex blurb.md>blurb.tex
	
blurb.html: blurb.md
	pandoc -f markdown -t html blurb.md>blurb.html
	
biosketch.tex: blurb.md
	pandoc -f markdown -t latex biosketch.md>biosketch.tex
	
biosketch.html: blurb.md
	pandoc -f markdown -t html biosketch.md>biosketch.html
	
#housekeeping	
clean:
	rm -f *.bak *~ *.backup *.tmp \
	*.adx *.and *.idx *.ind *.ldx *.lnd *.sdx *.snd *.rdx *.rnd *.wdx *.wnd \
	*.log *.blg *.ilg \
	*.aux *.toc *.cut *.out *.tpm *.bbl *-blx.bib *_tmp.bib \
	*.glg *.glo *.gls *.wrd *.wdv *.xdv \
	*.run.xml \
	chapters/*aux chapters/*~ chapters/*.bak chapters/*.backup

realclean: clean
	rm -f *.dvi *.ps *.pdf 

FORCE:
