# specify thh main file and all the files that you are including
SOURCE=  main.tex $(wildcard local*.tex) $(wildcard chapters/*.tex) 

# specify your main target here:
pdf: main.bbl main.pdf  #by the time main.pdf, bib assures there is a newer aux file
 
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
	sed -i 's/.*Office.*//' main.adx
	sed -i 's/.*Team.*//' main.adx
	sed -i 's/.*Bureau.*//' main.adx
	sed -i 's/.*Organisation.*//' main.adx
	sed -i 's/.*Embassy.*//' main.adx
	sed -i 's/.*Commission.*//' main.adx
	sed -i 's/.*SIL.*//' main.adx
	sed -i 's/.*Group.*//' main.adx
	sed -i 's/.MakeCapital//' main.sdx
	sed -i 's/accusative case/accusative/' main.sdx
	sed -i 's/adjectival/adjective/' main.sdx
	sed -i 's/aspectual meaning/aspect/' main.sdx
	sed -i 's/bare noun/noun/' main.sdx
	sed -i 's/colonial expansion/colonial period/' main.sdx
	sed -i 's/creole genesis theory/creole genesis/' main.sdx
	sed -i 's/completive aspect/aspect!completive/' main.sdx
	sed -i 's/durative aspect/aspect!durative/' main.sdx
	sed -i 's/perfect aspect/aspect!perfect/' main.sdx
	sed -i 's/progressive aspect/aspect!progressive/' main.sdx
	sed -i 's/expletive/profanity/' main.sdx
	sed -i 's/finite copula/copula/' main.sdx
	sed -i 's/genitive case/genitive/' main.sdx
	sed -i 's/gerund phrase/gerund/' main.sdx
	sed -i 's/subject noun/grammatical subject/' main.sdx
	sed -i 's/indicative mood/indicative modality/' main.sdx
	sed -i 's/late //' main.sdx
	sed -i 's/long boat/longboat/' main.sdx
	sed -i 's/maritime language/maritime speech/' main.sdx
	sed -i 's/main clause/matrix clause/' main.sdx
	sed -i 's/primary clause/matrix clause/' main.sdx
	sed -i 's/negation marker/negation/' main.sdx
	sed -i 's/negative concord/negation/' main.sdx
	sed -i 's/new dialect formation/new dialect/' main.sdx
	sed -i 's/noun head/noun phrase/' main.sdx
	sed -i 's/preterit/past tense/' main.sdx
	sed -i 's/past tense marking/past tense/' main.sdx
	sed -i 's/Pidgin/pidgin/' main.sdx
	sed -i 's/plural form/plural/' main.sdx
	sed -i 's/reflexive pronoun/pronoun/' main.sdx
	sed -i 's/realis marker/realis/' main.sdx
	sed -i 's/seamen/seaman/' main.sdx
	sed -i 's/tense marking/tense/' main.sdx
	sed -i 's/third person singular/third person/' main.sdx
	sed -i 's/singular third person/third person/' main.sdx
	sed -i 's/transitive verb/transitive/' main.sdx
	sed -i 's/creole/Creole/' main.sdx
	sed -i 's/hyperindexformat{\\\(infn {[0-9]*\)}/\1/' main.ldx
	python3 fixindex.py
	mv mainmod.adx main.adx
	makeindex -o main.and main.adx
	makeindex -o main.lnd main.ldx
	makeindex -o main.snd main.sdx 
	xelatex main 
 

#create a png of the cover
cover: FORCE
	convert main.pdf\[0\] -quality 100 -background white -alpha remove -bordercolor "#999999" -border 2  cover.png
	cp cover.png googlebooks_frontcover.png
	convert -geometry 50x50% cover.png covertwitter.png
	convert main.pdf\[0\] -quality 100 -background white -alpha remove -bordercolor "#999999" -border 2  -resize x495 coveromp.png
	display cover.png


googlebooks: googlebooks_interior.pdf

googlebooks_interior.pdf: 
	cp main.pdf googlebooks_interior.pdf
	pdftk main.pdf cat 1 output googlebooks_frontcover.pdf 

openreview: openreview.pdf
	

openreview.pdf: 
	pdftk main.pdf multistamp orstamp.pdf output openreview.pdf 

proofreading: proofreading.pdf
	
githubrepo: localmetadata.tex proofreading versions.json
	grep lsID localmetadata.tex |egrep -o "[0-9]*" > ID	
	git clone https://github.com/langsci/`cat ID`.git
	cp proofreading.pdf Makefile versions.json `cat ID`
	mv `cat ID` ..
	
versions.json: 
	grep "^.title{" localmetadata.tex|grep -o "{.*"|egrep -o "[^{}]+">title
# 	grep "^.BookDOI{" localmetadata.tex|grep -o "{.*"|egrep -o "[^{}]+">doi
	grep "^.author{" localmetadata.tex|grep -o "{.*"|egrep -o "[^{}]+" |sed 's/\\\(last\)\?and/"},{"name":"/g'>author
	echo '{"versions": [{"versiontype": "proofreading",' >versions.json
	echo -n '		"title": "' >>versions.json
	echo -n `cat title` >> versions.json
	echo  '",' >> versions.json
	echo -n  '		"authors": [{"name": "'>> versions.json
	echo -n `cat author` >> versions.json 
	echo  '"}],' >> versions.json 
	echo  '	"license": "CC-BY-4.0",'>> versions.json
# 	echo -n '	"DOI": "'>> versions.json
# 	echo -n `cat doi` >> versions.json	
# 	echo '",' >> versions.json
	echo -n '	"publishedAt": "' >> versions.json
	echo -n `date --rfc-3339=s|sed s/" "/T/|sed s/+.*/.000Z/` >> versions.json
	echo -n '"'>> versions.json
	echo  '}'>> versions.json
	echo  '	]'>> versions.json
	echo  '}'>> versions.json
	rm author title
	
paperhive:  
	git branch gh-pages
	git checkout gh-pages
	git add proofreading.pdf versions.json
	git commit -m 'prepare for proofreading' proofreading.pdf versions.json
	git push origin gh-pages
	grep lsID localmetadata.tex |egrep -o "[0-9]*" > ID
	sleep 3
	curl -X POST 'https://paperhive.org/api/document-items/remote?type=langsci&id='`cat ID`
	git checkout master 
	
proofreading.pdf:
	pdftk main.pdf multistamp prstamp.pdf output proofreading.pdf 
	
	
chop:  
	egrep -o "\{[0-9]+\}\{chapter\*\.[0-9]+\}" main.toc| egrep -o "[0-9]+\}\{chapter"|egrep -o [0-9]+ > cuts.txt
	egrep -o "\{chapter\}\{Index\}\{[0-9]+\}\{section\*\.[0-9]+\}" main.toc| grep -o "\..*"|egrep -o [0-9]+ >> cuts.txt
	bash chopchapters.sh `grep "mainmatter starts" main.log|grep -o "[0-9]*"`
	
#housekeeping	
clean:
	rm -f *.bak *~ *.backup *.tmp \
	*.adx *.and *.idx *.ind *.ldx *.lnd *.sdx *.snd *.rdx *.rnd *.wdx *.wnd \
	*.log *.blg *.ilg \
	*.aux *.toc *.cut *.out *.tpm *.bbl *-blx.bib *_tmp.bib *bcf \
	*.glg *.glo *.gls *.wrd *.wdv *.xdv *.mw *.clr *.pgs\
	*.run.xml \
	chapters/*aux chapters/*~ chapters/*.bak chapters/*.backup\
	langsci/*/*aux langsci/*/*~ langsci/*/*.bak langsci/*/*.backup

realclean: clean
	rm -f *.dvi *.ps *.pdf

chapterlist:
	grep chapter main.toc|sed "s/.*numberline {[0-9]\+}\(.*\).newline.*/\\1/" 


barechapters:
	cat chapters/*tex | detex > barechapters.txt

languagecandidates:
	egrep -oh "[a-z] [A-Z][a-z]+" chapters/*tex| grep -o  [A-Z].* |sort -u >languagelist.txt


FORCE:


supersede: convert cover.png -fill white -colorize 60%  -pointsize 64 -draw "gravity center fill red rotate -45  text 0,12 'superseded' "  superseded.png; display superseded.png
