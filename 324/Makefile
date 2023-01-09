# specify thh main file and all the files that you are including
SOURCE=  main.tex $(wildcard local*.tex) $(wildcard chapters/*.tex) 

# specify your main target here:
pdf: main.bbl main.pdf  #by the time main.pdf, bib assures there is a newer aux file

all: pod cover

complete: index main.pdf

index:  main.snd
 
main.pdf: main.aux
	xelatex main 

main.aux: $(SOURCE)
	xelatex -no-pdf main 

#create only the book
main.bbl:  $(SOURCE) localbibliography.bib  
	xelatex -no-pdf main 
	biber   main 


main.snd: main.bbl
	touch main.adx main.sdx main.ldx
	sed -i s/.*\\emph.*// main.adx #remove titles which biblatex puts into the name index
	sed -i 's/hyperindexformat{\\\(infn {[0-9]*\)}/\1/' main.sdx # ordering of references to footnotes
	sed -i 's/hyperindexformat{\\\(infn {[0-9]*\)}/\1/' main.adx
	sed -i 's/hyperindexformat{\\\(infn {[0-9]*\)}/\1/' main.ldx
	sed -i 's/.*INALI.*//' main.adx
	sed -i 's/.*Equative.*//' main.adx
	sed -i 's/{Norogachi Rarámuri/{Rarámuri!Norogachi Rarámuri/' main.ldx
	sed -i 's/{Samachique Rarámuri/{Rarámuri!Samachique Rarámuri/' main.ldx
	sed -i 's/{Western Rarámuri/{Rarámuri!Western Rarámuri (Tarahumara)/' main.ldx
	sed -i 's/{Western Tarahumara/{Rarámuri!Western Rarámuri (Tarahumara)/' main.ldx
	sed -i 's/{Pahuírachic Rarámuri/{Rarámuri!Pahuírachic Rarámuri/' main.ldx
	sed -i 's/{Rochéachi Rarámuri/{Rarámuri!Rochéachi Rarámuri/' main.ldx
	sed -i 's/{Ojachichi Rarámuri/{Rarámuri!Ojachichi Rarámuri/' main.ldx
	sed -i 's/{Urique Tarahumara/{Rarámuri!Urique Tarahumara (Rarómari)/' main.ldx
	sed -i 's/{Urique Rarómari/{Rarámuri!Urique Tarahumara (Rarómari)/' main.ldx
	sed -i 's/{Warihio/{Guarijío/' main.ldx
	sed -i 's/{Guarijio/{Guarijío/' main.ldx
	sed -i 's/{River Guarijío/{Guarijío!River Guarijío/' main.ldx
	sed -i 's/{Mountain Guarijío/{Guarijío!Mountain Guarijío/' main.ldx
	sed -i 's/{(River) Guarijío/{Guarijío!River Guarijío/' main.ldx
	sed -i 's/{(Mountain) Guarijío/{Guarijío!Mountain Guarijío/' main.ldx
	sed -i 's/{Northern Tepehuan/{Tepehuan!Northern Tepehuan/' main.ldx
	sed -i 's/{Southeastern Tepehuan/{Tepehuan!Southeastern Tepehuan/' main.ldx
	sed -i 's/{Southern Tepehuan/{Tepehuan!Southern Tepehuan/' main.ldx
	sed -i 's/{Santa María de Ocotán Tepehuan/{Tepehuan!Santa María de Ocotán Tepehuan/' main.ldx
	sed -i 's/{Balsas Nahuatl/{Nahuatl!Balsas Nahuatl/' main.ldx
	sed -i 's/{Milpa Alta Nahuatl/{Nahuatl!Milpa Alta Nahuatl/' main.ldx
	sed -i 's/{Southern Uto-Aztecan/{Uto-Aztecan!Southern Uto-Aztecan/' main.ldx
	sed -i 's/{Northern Uto-Aztecan/{Uto-Aztecan!Northern Uto-Aztecan/' main.ldx
	sed -i 's/{Proto-Uto-Aztecan/{Uto-Aztecan!Proto-Uto-Aztecan/' main.ldx
	sed -i 's/{Proto Uto-Aztecan/{Uto-Aztecan!Proto-Uto-Aztecan/' main.ldx
	sed -i 's/{Proto Northern Uto-Aztecan/{Uto-Aztecan!Proto Northern Uto-Aztecan/' main.ldx
	sed -i 's/{Proto Southern Uto-Aztecan/{Uto-Aztecan!Proto Southern Uto-Aztecan/' main.ldx
	sed -i 's/{Southern Nevada Northern Paiute/{Northern Paiute!Southern Nevada Northern Paiute /' main.ldx
	sed -i 's/{Mono Lake Northern Paiute/{Northern Paiute!Mono Lake Northern Paiute/' main.ldx
	sed -i 's/{Azkoitia Basque/{Basque!Azkoitia Basque/' main.ldx
	sed -i 's/{Proto-Sonoran/{Sonoran!Proto-Sonoran/' main.ldx
	sed -i 's/{Tukanoan/{Tucanoan/' main.ldx
	sed -i 's/{Stockholm Swedish/{Swedish!Stockholm Swedish/' main.ldx
	sed -i 's/{Imbabura Quechua/{Quechua!Imbabura Quechua/' main.ldx
	sed -i 's/{Tokyo Japanese/{Japanese!Tokyo Japanese/' main.ldx
	sed -i 's/{Curacao Papiamentu/{Papiamentu/' main.ldx
	sed -i 's/{Icua Tupi/{Tupi!Icua Tupi/' main.ldx
	sed -i 's/{Ituñoso Trique/{Trique!Ituñoso Trique/' main.ldx
	sed -i 's/{San Pablo Güilá Zapotec/{Zapotec!San Pablo Güilá Zapotec/' main.ldx
	sed -i 's/{Tümpisa Shoshone/{Shoshone!Tümpisa Shoshone/' main.ldx
	sed -i 's/{Wishram Chinook/{Chinook!Wishram Chinook/' main.ldx
	sed -i 's/{Lower Pima/{Pima!Lower Pima/' main.ldx
	sed -i "s/{O’ob Nook Pima/{Pima!O’ob Nook Pima/" main.ldx
	sed -i "s/{Taracahitic/Taracahitan/" main.ldx
	python3 fixindex.py
	makeindex -o main.and main.adx
	makeindex -o main.lnd main.ldx
	xelatex main 
 

#create a png of the cover
cover: FORCE
	convert main.pdf\[0\] -quality 100 -background white -alpha remove -bordercolor "#999999" -border 2  cover.png
	cp cover.png googlebooks_frontcover.png
	convert -geometry 50x50% cover.png covertwitter.png
	convert main.pdf\[0\] -quality 100 -background white -alpha remove -bordercolor "#999999" -border 2  -resize x495 coveromp.png
	display cover.png


googlebooks: googlebooks_interior.pdf

googlebooks_interior.pdf: complete
	cp main.pdf googlebooks_interior.pdf
	pdftk main.pdf cat 1 output googlebooks_frontcover.pdf 

openreview: openreview.pdf
	

openreview.pdf: main.pdf
	pdftk main.pdf multistamp orstamp.pdf output openreview.pdf 

proofreading: proofreading.pdf
	
paperhive: 
	git branch gh-pages
	git checkout gh-pages
	git add proofreading.pdf versions.json
	git commit -m 'prepare for proofreading' proofreading.pdf versions.json
	git push origin gh-pages
	git checkout master 
	echo "langsci.github.io/BOOKID"
	firefox https://paperhive.org/documents/new
	
proofreading.pdf: main.pdf
	pdftk main.pdf multistamp prstamp.pdf output proofreading.pdf 

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
	*.glg *.glo *.gls *.wrd *.wdv *.xdv *.mw *.clr \
	*.run.xml \
	chapters/*aux chapters/*~ chapters/*.bak chapters/*.backup\
	langsci/*/*aux langsci/*/*~ langsci/*/*.bak langsci/*/*.backup

realclean: clean
	rm -f *.dvi *.ps *.pdf

chapterlist:
	grep chapter main.toc|sed "s/.*numberline {[0-9]\+}\(.*\).newline.*/\\1/" 

podcover:
	bash podcovers.sh

 

FORCE:
