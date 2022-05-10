# specify thh riessler file and all the files that you are including
SOURCE=  riessler.tex $(wildcard local*.tex) $(wildcard chapters/*.tex) \
langsci/langscibook.cls

# specify your riessler target here:
pdf: riessler.bbl riessler.pdf  #by the time riessler.pdf, bib assures there is a newer aux file

all: pod cover

complete: index riessler.pdf

index:  riessler.and
 
riessler.pdf: riessler.aux
	xelatex riessler 

riessler.aux: $(SOURCE)
	xelatex -no-pdf riessler 

#create only the book
riessler.bbl:  $(SOURCE) localbibliography.bib  
	xelatex -no-pdf riessler 
# 	biber -min-crossrefs=200 riessler 
	bibtex  -min-crossrefs=200 riessler 

riessler.and: riessler.bbl
	sed -i s/.*\\emph.*// riessler.adx #remove titles which biblatex puts into the name index
	sed -i 's/Testelets, Jakov~G/Testelets, Yakov~G/' riessler.adx 
	sed -i 's/Volodin, Aleksandr~P./Volodin, Alexander~P./' riessler.adx 
	sed -i 's/Schulze, Wolfgang/Schulze-Fürhoff, Wolfgang/' riessler.adx 
	sed -i 's/Nikolaeva, Irina~A./Nikolaeva, Irina/' riessler.adx 
	sed -i 's/Nedjalkov, Igor~V./Nedjalkov, Igor/' riessler.adx 
	sed -i 's/hyperindexformat{\\\(infn {[0-9]*\)}/\1/' riessler.sdx # ordering of references to footnotes
	sed -i 's/hyperindexformat{\\\(infn {[0-9]*\)}/\1/' riessler.adx
	sed -i 's/hyperindexformat{\\\(infn {[0-9]*\)}/\1/' riessler.ldx
	python3 fixindex.py
	mv mainmod.adx riessler.adx
	makeindex -o riessler.and riessler.adx
	makeindex -o riessler.lnd riessler.ldx
	makeindex -o riessler.snd riessler.sdx 
	xelatex riessler 
 

#create a png of the cover
cover: FORCE
	convert riessler.pdf\[0\] -quality 100 -background white -alpha remove -bordercolor black -border 2  cover.png
	cp cover.png googlebooks_frontcover.png
	convert -geometry 50x50% cover.png covertwitter.png
	display cover.png
 
	
#prepare for print on demand services	
pod: bod createspace googlebooks
 
#prepare for submission to BOD
bod: bod/bodcontent.pdf 

bod/bodcontent.pdf: complete
	sed "s/output=short/output=coverbod/" riessler.tex >bodcover.tex 
	xelatex bodcover.tex  
	xelatex bodcover.tex  
	mv bodcover.pdf bod
	./filluppages 4 riessler.pdf bod/bodcontent.pdf 

# prepare for submission to createspace
createspace:  createspace/createspacecontent.pdf 

createspace/createspacecontent.pdf: complete
	sed "s/output=short/output=covercreatespace/" riessler.tex >createspacecover.tex 
	xelatex createspacecover.tex 
	xelatex createspacecover.tex 
	mv createspacecover.pdf createspace
	c
googlebooks: googlebooks_interior.pdf

googlebooks_interior.pdf: complete
	cp riessler.pdf googlebooks_interior.pdf
	pdftk riessler.pdf cat 1 output googlebooks_frontcover.pdf 

openreview: openreview.pdf
	

openreview.pdf: riessler.pdf
	pdftk riessler.pdf multistamp orstamp.pdf output openreview.pdf 

proofreading: proofreading.pdf
	

proofreading.pdf: riessler.pdf
	pdftk riessler.pdf multistamp prstamp.pdf output proofreading.pdf 

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
