STYLE-PATH= ${HOME}/Library/texmf/tex/latex/
SOURCE=  main.tex $(wildcard local*.tex) $(wildcard chapters/*.tex) localbibliography.bib stmue.bib \
langscibook.cls 
OPTIONS=-output-driver="xdvipdfmx -i dvipdfmx-unsafe.cfg -q -E"

#langsci-unified.bbx langsci-forest-setup.sty



main.pdf: $(SOURCE)
	xelatex -shell-escape $(OPTIONS) main
	biber main
	xelatex -shell-escape $(OPTIONS) main
	sed -i.backup s/.*\\emph.*// main.adx #remove titles which biblatex puts into the name index
# sed -i.backup 's/hyperindexformat{\\\(infn {[0-9]*\)}/\1/' main.sdx # ordering of references to footnotes
# sed -i.backup 's/hyperindexformat{\\\(infn {[0-9]*\)}/\1/' main.adx
# sed -i.backup 's/hyperindexformat{\\\(infn {[0-9]*\)}/\1/' main.ldx
	sed -i.backup 's/\\MakeCapital //g' main.adx
	python3 fixindex.py
	mv mainmod.adx main.adx
	footnotes-index.pl main.ldx
	footnotes-index.pl main.sdx
	footnotes-index.pl main.adx 
	makeindex -o main.and main.adx
	makeindex -gs index.format -o main.lnd main.ldx
	makeindex -gs index.format -o main.snd main.sdx 
	xelatex -shell-escape $(OPTIONS) main

check-index:
	xelatex -shell-escape $(OPTIONS) main
	sed -i.backup s/.*\\emph.*// main.adx #remove titles which biblatex puts into the name index
# sed -i.backup 's/hyperindexformat{\\\(infn {[0-9]*\)}/\1/' main.sdx # ordering of references to footnotes
# sed -i.backup 's/hyperindexformat{\\\(infn {[0-9]*\)}/\1/' main.adx
# sed -i.backup 's/hyperindexformat{\\\(infn {[0-9]*\)}/\1/' main.ldx
	sed -i.backup 's/\\MakeCapital //g' main.adx
	python3 fixindex.py
	mv mainmod.adx main.adx
	footnotes-index.pl main.ldx
	footnotes-index.pl main.sdx
	footnotes-index.pl main.adx 
	makeindex -o main.and main.adx
	makeindex -gs index.format -o main.lnd main.ldx
	makeindex -gs index.format -o main.snd main.sdx 
	xelatex -shell-escape $(OPTIONS) main

stable.pdf: main.pdf
	cp main.pdf stable.pdf
	cp collection_tmp.bib chapters/collection.bib

#create a png of the cover
cover: FORCE
	convert main.pdf\[0\] -quality 100 -background white -alpha remove -bordercolor "#999999" -border 2  cover.png
	cp cover.png googlebooks_frontcover.png
	convert -geometry 50x50% cover.png covertwitter.png

# ggrep is gnu grep, needed on a Mac since Apple broke the -P option.
# use brew install grep to install it
# Then call python3 autoindex.py
languagecandidates:
	ggrep -ohP "(?<=[a-z]|[0-9])(\))?(,)? (\()?[A-Z]['a-zA-Z-]+" chapters/*tex| grep -o  [A-Z].* |sort -u >languagelist.txt


stmue-install:
	cp -p ${STYLE-PATH}makros.2020.sty                   styles/
	cp -p ${STYLE-PATH}abbrev.sty                        styles/
	cp -p ${STYLE-PATH}eng-date.sty                      styles/
	cp -p ${STYLE-PATH}biblatex-series-number-checks.sty styles/
	cp -p ${STYLE-PATH}Ling/article-ex.sty               styles/
	cp -p ${STYLE-PATH}Ling/merkmalstruktur.sty          styles/






# the index is irrelevant so I removed index creation here
prepublish.pdf: $(SOURCE) prepublish.tex
	xelatex -no-pdf -shell-escape prepublish
	biber prepublish
	xelatex -no-pdf -shell-escape prepublish
	xelatex -shell-escape prepublish


prepublish-pdfs: prepublish.pdf
	chopchapters-bookmarks.sh prepublish.pdf prepubs-chop-pdfs


prepubs-pdfs/lander.pdf: prepublish-pdfs
	cp prepubs-chop-pdfs/02.pdf prepubs-pdfs/lander.pdf

prepubs-pdfs/salzmann.pdf: prepublish-pdfs
	cp prepubs-chop-pdfs/03.pdf prepubs-pdfs/salzmann.pdf

prepubs-pdfs/mueller.pdf: prepublish-pdfs
	cp prepubs-chop-pdfs/04.pdf prepubs-pdfs/mueller.pdf

prepubs-pdfs/demske.pdf: prepublish-pdfs
	cp prepubs-chop-pdfs/05.pdf prepubs-pdfs/demske.pdf

prepubs-pdfs/korth.pdf: prepublish-pdfs
	cp prepubs-chop-pdfs/06.pdf prepubs-pdfs/korth.pdf

prepubs-pdfs/haider.pdf: prepublish-pdfs
	cp prepubs-chop-pdfs/07.pdf prepubs-pdfs/haider.pdf

prepubs-pdfs/noel.pdf: prepublish-pdfs
	cp prepubs-chop-pdfs/09.pdf prepubs-pdfs/noel.pdf

prepubs-pdfs/buecker.pdf: prepublish-pdfs
	cp prepubs-chop-pdfs/10.pdf prepubs-pdfs/buecker.pdf

prepubs-pdfs/nolda.pdf: prepublish-pdfs
	cp prepubs-chop-pdfs/11.pdf prepubs-pdfs/nolda.pdf

prepublish: prepubs-pdfs/lander.pdf\
        prepubs-pdfs/salzmann.pdf\
	prepubs-pdfs/mueller.pdf\
	prepubs-pdfs/demske.pdf\
	prepubs-pdfs/korth.pdf\
	prepubs-pdfs/haider.pdf\
	prepubs-pdfs/noel.pdf\
	prepubs-pdfs/buecker.pdf\
	prepubs-pdfs/nolda.pdf


todo-localbib.unique.txt: main.bcf localbibliography.bib
	biber -V main | grep -i warn | grep localbib | sort -uf > todo-localbib.unique.txt



references.pdf: references.tex localbibliography.bib stmue.bib
	xelatex references
	biber references
	xelatex references

clean:
	rm -f *.bak *~ *.backup \
	*.adx *.and *.idx *.ind *.ldx *.lnd *.sdx *.snd *.rdx *.rnd *.wdx *.wnd \
	*.log *.blg *.bcf *.aux.copy *.auxlock *.ilg \
	*.aux *.toc *.cut *.out *.tpm *.bbl *-blx.bib *_tmp.bib \
	*.glg *.glo *.gls *.wrd *.wdv *.xdv *.mw *.clr *.thm \
	*.run.xml \
	chapters/*.aux chapters/*.auxlock chapters/*.aux.copy chapters/*.old chapters/*~ chapters/*.bak chapters/*.backup chapters/*.blg\
	chapters/*.log chapters/*.out chapters/*.mw chapters/*.ldx  chapters/*.bbl chapters/*.bcf chapters/*.run.xml\
	chapters/*.blg chapters/*.idx chapters/*.sdx chapters/*.run.xml chapters/*.adx chapters/*.ldx\
	langsci/*/*.aux langsci/*/*~ langsci/*/*.bak langsci/*/*.backup \
	chapter-pdfs/* cuts.txt


FORCE:
