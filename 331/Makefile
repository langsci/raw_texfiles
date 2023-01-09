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
	sed -i 's/hyperindexformat{\\\(infn {[0-9]*\)}/\1/' main.ldx
	sed -i 's/.*Office.*//' main.adx
	sed -i 's/.*Team.*//' main.adx
	sed -i 's/.*Bureau.*//' main.adx
	sed -i 's/.*Organisation.*//' main.adx
	sed -i 's/.*Organization.*//' main.adx
	sed -i 's/.*Embassy.*//' main.adx
	sed -i 's/.*Association.*//' main.adx
	sed -i 's/.*Commission.*//' main.adx
	sed -i 's/.*committee.*//' main.adx
	sed -i 's/.*government.*//' main.adx
	sed -i 's/\\MakeCapital//' main.adx
	sed -i 's/OHG/Old High German/' main.ldx
	sed -i 's/OSax/Old Saxon/' main.ldx
	sed -i 's/MHG/Middle High German/' main.ldx
	sed -i 's/MLG/Middle Low German/' main.ldx
	sed -i 's/ENHG/Early New High German/' main.ldx
	sed -i 's/OE/Old English/' main.ldx
	sed -i 's/ME/Middle English/' main.ldx
	sed -i 's/OFr/Old Frisian/' main.ldx
	sed -i 's/OLF/Old Low Franconian/' main.ldx
	sed -i 's/ON/Old Norse/' main.ldx
	sed -i 's/Go|/Gothic|/' main.ldx
	sed -i 's/PGmc/Proto-Germanic/' main.ldx
	sed -i 's/PIE/Proto-Indo European/' main.ldx
	sed -i 's/NGmc/North Germanic/' main.ldx
	sed -i 's/EGmc/East Germanic/' main.ldx
	sed -i 's/WGmc/West Germanic/' main.ldx
	sed -i 's/StAG/Standard Austrian German/' main.ldx
	sed -i 's/StSwG/Standard Swiss German/' main.ldx
	sed -i 's/OCP|/Obligatory~Contour Principle (OCP)|/' main.sdx
	sed -i 's/Obligatory Contour Principle|/Obligatory~Contour Principle (OCP)|/' main.sdx
	sed -i 's/{Velar Fronting-10|/{Velar Froting-9a@Velar Fronting-10|/' main.sdx
	sed -i 's/{Velar Fronting-11|/{Velar Froting-9b@Velar Fronting-11|/' main.sdx
	sed -i 's/{Velar Fronting-12|/{Velar Froting-9c@Velar Fronting-12|/' main.sdx
	sed -i 's/{Velar Fronting-13|/{Velar Froting-9d@Velar Fronting-13|/' main.sdx
	sed -i 's/{Velar Fronting-14|/{Velar Froting-9e@Velar Fronting-14|/' main.sdx
	sed -i 's/{alveolopalatalizing islands/{alveolopalatalizing island/' main.sdx
	sed -i 's/{assibilations/{assibilation/' main.sdx
	sed -i 's/{counterbleeds/{counterbleeding/' main.sdx
	sed -i 's/{ethnolects/{ethnolect//' main.sdx
	sed -i 's/{lexical exceptions/{lexical exception/' main.sdx
	sed -i 's/{Margin Hierarchies/{Margin Hierarchy/' main.sdx
	sed -i 's/{Mutual bleeding/{mutual bleeding order/' main.sdx
	sed -i 's/{Rule reordering/{rule reordering/' main.sdx
	sed -i 's/{reordered/{rule reordering/' main.sdx
	sed -i 's/{velar fronting islands/{velar fronting island/' main.sdx
	sed -i 's/{Walser migrations/{Walser migration/' main.sdx
	sed -i 's/{Walser Migrations/{Walser migration/' main.sdx
	sed -i 's/{Walser variety of HstAlmc/Walser German/' main.sdx
	sed -i 's/{Wd-initial/Wd-Initial/' main.sdx
	sed -i 's/{non-velar fronting islands/{non-velar fronting island/' main.sdx
	sed -i 's/{bleeding|/{bleeding order|/' main.sdx
	sed -i 's/{bleeds|/{bleeding order|/' main.sdx
	sed -i 's/{bleed|/{bleeding order|/' main.sdx
	sed -i 's/{Counterfeeding|/{counterfeeding order|/' main.sdx
	sed -i 's/{counterfeeding|/{counterfeeding order|/' main.sdx
	sed -i 's/{counterfeeds|/{counterfeeding order|/' main.sdx
	sed -i 's/{counterfeed|/{counterfeeding order|/' main.sdx
	sed -i 's/{counterbleeding|/{counterbleeding order|/' main.sdx
	sed -i 's/{counterbleeding ordering|/{counterbleeding order|/' main.sdx
	sed -i 's/{counterbleeds|/{counterbleeding order|/' main.sdx
	sed -i 's/{counterbleed|/{counterbleeding order|/' main.sdx
	sed -i 's/{feeding|/{feeding order|/' main.sdx
	sed -i 's/{Feeding order|/{feeding order|/' main.sdx
	sed -i 's/{feeds|/{feeding order|/' main.sdx
	sed -i 's/{feed|/{feeding order|/' main.sdx
	sed -i 's/{derived palatals/{derived palatal/' main.sdx
	sed -i 's/{Derived palatals/{derived palatal/' main.sdx
	sed -i 's/{Derived palatal/{derived palatal/' main.sdx
	sed -i 's/{diglossic/{diglossia/' main.sdx
	sed -i 's/{full vowels/{full vowel/' main.sdx
	sed -i 's/{Full vowels/{full vowel/' main.sdx
	sed -i 's/{Neutral vowels/{neutral vowel/' main.sdx
	sed -i 's/{neutral vowels/{neutral vowel/' main.sdx
	sed -i 's/{Nonheight feature/{nonheight feature/' main.sdx
	sed -i 's/{nonheight features/{nonheight feature/' main.sdx
	sed -i 's/{nonneutral|/{nonneutral vowel|/' main.sdx
	sed -i 's/{nonneutral vowels|/{nonneutral vowel|/' main.sdx
	sed -i 's/{phonetic rules/{phonetic rule/' main.sdx
	sed -i 's/{Phonetic rule/{phonetic rule/' main.sdx
	sed -i 's/{prevelars/{prevelar/' main.sdx
	sed -i 's/{velar palatalizations/{Velar Palatalization/' main.sdx
	sed -i 's/{Velar palatalization/{Velar Palatalization/' main.sdx
	sed -i 's/{Velar Palatalization/{Velar Palatalization/' main.sdx
	sed -i 's/{lip rounding/{rounding/' main.sdx
	sed -i 's/{Rounding/{rounding/' main.sdx
	sed -i 's/{Tenseness/{tenseness/' main.sdx
	sed -i 's/{Alveolopalatalization/{alveolopalatalization/' main.sdx
	sed -i 's/{central vowels/{central vowel/' main.sdx
	sed -i 's/{Directionality/{directionality/' main.sdx
	sed -i 's/{mutually bleeding/{mutual bleeding order/' main.sdx
	sed -i 's/{Phonemicization/phonemicization/' main.sdx
	sed -i 's/{Phonetic retraction/phonetic retraction/' main.sdx
	sed -i 's/{Stress/stress/' main.sdx
	python3 fixindex.py ap
	mv mainmod.adx main.adx
	mv mainmod.pdx main.pdx
	makeindex -o main.and main.adx
	makeindex -o main.lnd main.ldx
	makeindex -o main.snd main.sdx
	makeindex -o main.pnd main.pdx
	xelatex main


#create a png of the cover
cover: FORCE
	convert main.pdf\[0\] -quality 100 -background white -alpha remove -bordercolor "#999999" -border 2  cover.png
	cp cover.png googlebooks_frontcover.png
	convert -geometry 50x50% cover.png covertwitter.png
	convert main.pdf\[0\] -quality 100 -background white -alpha remove -bordercolor "#999999" -border 2  -resize x495 coveromp.png
	display cover.png

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
	grep "^.author{" localmetadata.tex|grep -o "{.*"|egrep -o "[^{}]+" |sed 's/ and/"},{"name":"/g'>author
	echo '{"versions": [{"versiontype": "proofreading",' >versions.json
	echo -n '		"title": "' >>versions.json
	echo -n `cat title` >> versions.json
	echo  '",' >> versions.json
	echo -n  '		"authors": [{"name": "'>> versions.json
	echo -n `cat author` >> versions.json 
	echo  '"}],' >> versions.json 
	echo  '	"license": "CC-BY-4.0",'>> versions.json
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
	git checkout main 
		
firstedition:
	git checkout gh-pages
	git pull origin gh-pages
	basename `pwd` > ID
	python getfirstedition.py  `cat ID`
	git add first_edition.pdf 
	git commit -am 'provide first edition'
	git push origin gh-pages 
	git checkout main 
	curl -X POST 'https://paperhive.org/api/document-items/remote?type=langsci&id='`cat ID`
	
	
proofreading.pdf:
	pdftk main.pdf multistamp prstamp.pdf output proofreading.pdf 
	
	
chop:  
	egrep -o "\{[0-9]+\}\{chapter\.[0-9]+\}" main.toc| egrep -o "[0-9]+\}\{chapter"|egrep -o [0-9]+ > cuts.txt
	egrep -o "\{chapter\}\{Index\}\{[0-9]+\}\{section\*\.[0-9]+\}" main.toc| grep -o "\..*"|egrep -o [0-9]+ >> cuts.txt
	bash chopchapters.sh `grep "mainmatter starts" main.log|grep -o "[0-9]*" $1 $2`
	
chapternames:
	egrep -o "\{chapter\}\{\\\numberline \{[0-9]+}[A-Z][^\}]+\}" main.toc | egrep -o "[[:upper:]][^\}]+" > chapternames	
	
#housekeeping	
clean:
	rm -f *.bak *~ *.backup *.tmp \
	*.adx *.and *.idx *.ind *.ldx *.lnd *.sdx *.snd *.rdx *.rnd *.wdx *.wnd \
	*.log *.blg *.ilg \
	*.aux *.toc *.cut *.out *.tpm *.bbl *-blx.bib *_tmp.bib *bcf \
	*.glg *.glo *.gls *.wrd *.wdv *.xdv *.mw *.clr *.pgs\
	main.run.xml\
	chapters/*aux chapters/*~ chapters/*.bak chapters/*.backup\
	langsci/*/*aux langsci/*/*~ langsci/*/*.bak langsci/*/*.backup

realclean: clean
	rm -f *.dvi *.ps *.pdf

chapterlist:
	grep chapter main.toc|sed "s/.*numberline {[0-9]\+}\(.*\).newline.*/\\1/" 


barechapters:
	cat chapters/*tex | detex > barechapters.txt

languagecandidates:
	grep -ohP "(?<=[a-z]|[0-9])(\))?(,)? (\()?[A-Z]['a-zA-Z-]+" chapters/*tex| grep -o  [A-Z].* |sort -u >languagelist.txt


FORCE:

README.md: 
	echo `grep title localmetadata.tex|sed "s/\\\\\title{\(.*\)}/\# \1/"` > README.md
	echo '## Publication Info' >> README.md
	echo -n '- Authors: ' >> README.md
	echo `grep author localmetadata.tex|sed "s/\\\\\author{\(.*\)}/\1/"` >> README.md
	echo "- Publication Date: not yet published" >> README.md
	echo -n "- Series: " >> README.md
	echo `grep "lsSeries}" localmetadata.tex|sed "s/.*lsSeries}{\(.*\)}/\1/"` >> README.md
	echo "## Description" >> README.md
	echo -n "[Book page on langsci-press.org](http://langsci-press.org/catalog/book/" >> README.md
	echo  `grep lsID localmetadata.tex|sed "s/.*lsID\}{\(.*\)}/\1)/"` >> README.md 
	echo "## License" >> README.md
	echo "Copyright: (c) 2017, the authors." >> README.md
	echo "All data, code and documentation in this repository is published under the [Creative Commons Attribution 4.0 Licence](http://creativecommons.org/licenses/by/4.0/) (CC BY 4.0)." >> README.md

	
supersede: convert cover.png -fill white -colorize 60%  -pointsize 64 -draw "gravity center fill red rotate -45  text 0,12 'superseded' "  superseded.png; display superseded.png


wikicite: 
	echo '<ref name="abc">{{Cite book' > wiki
	echo -n "| vauthors = " >>wiki; echo `grep author localmetadata.tex|sed "s/\\\\\author{\(.*\)}/\1/"`  >>wiki
	echo -n "| title =" >>wiki; echo `grep title localmetadata.tex|sed "s/\\\\\title{\(.*\)}/\1/"` >>wiki
	echo    "| place = Berlin" >>wiki 
	echo    "| publisher = Language Science Press" >>wiki
	echo    "| date = 2018" >>wiki
	echo    "| format = pdf" >>wiki
	echo -n "| url = http://langsci-press.org/catalog/book/"  >>wiki; echo `grep lsID localmetadata.tex|sed "s/.*lsID\}{\(.*\)}/\1/"` >>wiki
	echo -n "| doi =" >>wiki; echo `cat doi` >>wiki
	echo    "| doi-access=free" >>wiki
	echo -n "| isbn = " >>wiki;  echo `grep lsISBNdigital localmetadata.tex|sed "s/.*lsISBNdigital\}{\(.*\)}/\1)/"` >>wiki
	echo "}}" >>wiki
	echo " </ref>" >>wiki
	more wiki
