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
	sed -i -e 's/indexentry {Aeolic/indexentry {Ancient Greek!Aeolic/g' main.ldx
	sed -i -e 's/indexentry {Alexandrian/indexentry {Ancient Greek!Alexandrian/g' main.ldx
	sed -i -e 's/indexentry {Arcado-Cypriot/indexentry {Ancient Greek!Arcado-Cypriot/g' main.ldx
	sed -i -e 's/indexentry {Argive/indexentry {Ancient Greek!Argive/g' main.ldx
	sed -i -e 's/indexentry {Asian/indexentry {Ancient Greek!Asian/g' main.ldx
	sed -i -e 's/indexentry {Athenian/indexentry {Ancient Greek!Athenian/g' main.ldx
	sed -i -e 's/indexentry {Attic/indexentry {Ancient Greek!Attic/g' main.ldx
	sed -i -e 's/indexentry {Biblical/indexentry {Ancient Greek!Biblical/g' main.ldx
	sed -i -e 's/indexentry {Boeotian/indexentry {Ancient Greek!Boeotian/g' main.ldx
	sed -i -e 's/indexentry {Chalcidian/indexentry {Ancient Greek!Chalcidian/g' main.ldx
	sed -i -e 's/indexentry {Cretan/indexentry {Ancient Greek!Cretan/g' main.ldx
	sed -i -e 's/indexentry {Cypriot/indexentry {Ancient Greek!Cypriot/g' main.ldx
	sed -i -e 's/indexentry {Doric/indexentry {Ancient Greek!Doric/g' main.ldx
	sed -i -e 's/indexentry {Hebraizing/indexentry {Ancient Greek!Hebraizing/g' main.ldx
	sed -i -e 's/indexentry {Hellenic/indexentry {Ancient Greek!Hellenic/g' main.ldx
	sed -i -e 's/indexentry {Hellenistic/indexentry {Ancient Greek!Hellenistic/g' main.ldx
	sed -i -e 's/indexentry {Homeric/indexentry {Ancient Greek!Homeric/g' main.ldx
	sed -i -e 's/indexentry {Ionic/indexentry {Ancient Greek!Ionic/g' main.ldx
	sed -i -e 's/indexentry {Koine/indexentry {Ancient Greek!Koine/g' main.ldx
	sed -i -e 's/indexentry {Laconian/indexentry {Ancient Greek!Laconian/g' main.ldx
	sed -i -e 's/indexentry {Lesbian/indexentry {Ancient Greek!Lesbian/g' main.ldx
	sed -i -e 's/indexentry {Macedonian/indexentry {Ancient Greek!Macedonian/g' main.ldx
	sed -i -e 's/indexentry {New Testament/indexentry {Ancient Greek!New Testament/g' main.ldx
	sed -i -e 's/indexentry {North-West/indexentry {Ancient Greek!North-West/g' main.ldx
	sed -i -e 's/indexentry {Pamphylian/indexentry {Ancient Greek!Pamphylian/g' main.ldx
	sed -i -e 's/indexentry {Poetical/indexentry {Ancient Greek!Poetical/g' main.ldx
	sed -i -e 's/indexentry {Rhegian/indexentry {Ancient Greek!Rhegian/g' main.ldx
	sed -i -e 's/indexentry {Rhodian/indexentry {Ancient Greek!Rhodian/g' main.ldx
	sed -i -e 's/indexentry {Septuagint/indexentry {Ancient Greek!Septuagint/g' main.ldx
	sed -i -e 's/indexentry {Sicilian/indexentry {Ancient Greek!Sicilian/g' main.ldx
	sed -i -e 's/indexentry {Syracusan/indexentry {Ancient Greek!Syracusan/g' main.ldx
	sed -i -e 's/indexentry {Tarentine/indexentry {Ancient Greek!Tarentine/g' main.ldx
	sed -i -e 's/indexentry {Thessalian/indexentry {Ancient Greek!Thessalian/g' main.ldx
	sed -i -e 's/indexentry {Brabantian/indexentry {Dutch!Brabantian/g' main.ldx
	sed -i -e 's/indexentry {Flemish/indexentry {Dutch!Flemish/g' main.ldx
	sed -i -e 's/indexentry {Guelderish/indexentry {Dutch!Guelderish/g' main.ldx
	sed -i -e 's/indexentry {Hollandic/indexentry {Dutch!Hollandic/g' main.ldx
	sed -i -e 's/indexentry {Kleverlandish/indexentry {Dutch!Kleverlandish/g' main.ldx
	sed -i -e 's/indexentry {Poetical Dutch/indexentry {Dutch!Poetical/g' main.ldx
	sed -i -e 's/indexentry {Athenian/indexentry {Early Modern Greek@(Early) Modern Greek!Athenian/g' main.ldx
	sed -i -e 's/indexentry {Ceraunian Mountains/indexentry {Early Modern Greek@(Early) Modern Greek!Ceraunian Mountains/g' main.ldx
	sed -i -e 's/indexentry {Constantinopolitan/indexentry {Early Modern Greek@(Early) Modern Greek!Constantinopolitan/g' main.ldx
	sed -i -e 's/indexentry {Continental/indexentry {Early Modern Greek@(Early) Modern Greek!Continental/g' main.ldx
	sed -i -e 's/indexentry {Cretan/indexentry {Early Modern Greek@(Early) Modern Greek!Cretan/g' main.ldx
	sed -i -e 's/indexentry {Cypriot/indexentry {Early Modern Greek@(Early) Modern Greek!Cypriot/g' main.ldx
	sed -i -e 's/indexentry {Dimotikí/indexentry {Early Modern Greek@(Early) Modern Greek!Dimotikí@\\textit{Dimotikí}/g' main.ldx
	sed -i -e 's/indexentry {Insular/indexentry {Early Modern Greek@(Early) Modern Greek!Insular/g' main.ldx
	sed -i -e 's/indexentry {Ioannina/indexentry {Early Modern Greek@(Early) Modern Greek!Ioannina/g' main.ldx
	sed -i -e 's/indexentry {Katharévousa/indexentry {Early Modern Greek@(Early) Modern Greek!Katharévousa@\\textit{Katharévousa}/g' main.ldx
	sed -i -e 's/indexentry {Peloponnesian/indexentry {Early Modern Greek@(Early) Modern Greek!Peloponnesian/g' main.ldx
	sed -i -e 's/indexentry {Standard Modern/indexentry {Early Modern Greek@(Early) Modern Greek!Standard Modern/g' main.ldx
	sed -i -e 's/indexentry {Thessalonican/indexentry {Early Modern Greek@(Early) Modern Greek!Thessalonican/g' main.ldx
	sed -i -e 's/indexentry {Tsakonian/indexentry {Early Modern Greek@(Early) Modern Greek!Tsakonian/g' main.ldx
	sed -i -e 's/indexentry {Eastern English/indexentry {English!Eastern/g' main.ldx
	sed -i -e 's/indexentry {Northern English/indexentry {English!Northern/g' main.ldx
	sed -i -e 's/indexentry {Poetical English/indexentry {English!Poetical/g' main.ldx
	sed -i -e 's/indexentry {Scots/indexentry {English!Scots/g' main.ldx
	sed -i -e 's/indexentry {Southern English/indexentry {English!Southern/g' main.ldx
	sed -i -e 's/indexentry {Western English/indexentry {English!Western/g' main.ldx
	sed -i -e 's/indexentry {Somerset English/indexentry {English!Somerset/g' main.ldx
	sed -i -e 's/indexentry {Old French/indexentry {French!Old/g' main.ldx
	sed -i -e 's/indexentry {Parisian/indexentry {French!Parisian/g' main.ldx
	sed -i -e 's/indexentry {Franco-Provençal/indexentry {Gallo-Romance!Franco-Provençal/g' main.ldx
	sed -i -e 's/indexentry {Limousin/indexentry {Gallo-Romance!Limousin/g' main.ldx
	sed -i -e 's/indexentry {Lyonnais/indexentry {Gallo-Romance!Lyonnais/g' main.ldx
	sed -i -e 's/indexentry {Picard/indexentry {Gallo-Romance!Picard/g' main.ldx
	sed -i -e 's/indexentry {Provençal/indexentry {Gallo-Romance!Provençal/g' main.ldx
	sed -i -e 's/indexentry {Austrian/indexentry {German!Austrian/g' main.ldx
	sed -i -e 's/indexentry {Bavarian/indexentry {German!Bavarian/g' main.ldx
	sed -i -e 's/indexentry {East Upper German/indexentry {German!East Upper/g' main.ldx
	sed -i -e 's/indexentry {High German/indexentry {German!High/g' main.ldx
	sed -i -e 's/indexentry {Low German/indexentry {German!Low/g' main.ldx
	sed -i -e 's/indexentry {Low Saxon German/indexentry {German!Low Saxon/g' main.ldx
	sed -i -e 's/indexentry {Low Saxon/indexentry {German!Low Saxon/g' main.ldx
	sed -i -e 's/indexentry {Swiss/indexentry {German!Swiss/g' main.ldx
	sed -i -e 's/indexentry {Upper German/indexentry {German!Upper/g' main.ldx
	sed -i -e 's/indexentry {North Germanic/indexentry {Germanic!North/g' main.ldx
	sed -i -e 's/indexentry {West Germanic/indexentry {Germanic!West/g' main.ldx
	sed -i -e 's/indexentry {Biblical Hebrew/indexentry {Hebrew!Biblical/g' main.ldx
	sed -i -e 's/indexentry {Mishnaic Hebrew/indexentry {Hebrew!Mishnaic/g' main.ldx
	sed -i -e 's/indexentry {Poetical Hebrew/indexentry {Hebrew!Poetical/g' main.ldx
	sed -i -e 's/indexentry {Bergamasque/indexentry {Italo-Romance!Bergamasque/g' main.ldx
	sed -i -e 's/indexentry {Florentine/indexentry {Italo-Romance!Florentine/g' main.ldx
	sed -i -e 's/indexentry {Lombard/indexentry {Italo-Romance!Lombard/g' main.ldx
	sed -i -e 's/indexentry {Neapolitan/indexentry {Italo-Romance!Neapolitan/g' main.ldx
	sed -i -e 's/indexentry {Tuscan/indexentry {Italo-Romance!Tuscan/g' main.ldx
	sed -i -e 's/indexentry {Venetian/indexentry {Italo-Romance!Venetian/g' main.ldx
	sed -i -e 's/indexentry {Ancient Latin/indexentry {Latin!Ancient/g' main.ldx
	sed -i -e 's/indexentry {Classical Latin/indexentry {Latin!Classical/g' main.ldx
	sed -i -e 's/indexentry {Female Latin/indexentry {Latin!Female/g' main.ldx
	sed -i -e 's/indexentry {Mantuan/indexentry {Latin!Mantuan/g' main.ldx
	sed -i -e 's/indexentry {Mixed Latin/indexentry {Latin!Mixed/g' main.ldx
	sed -i -e 's/indexentry {Paduan/indexentry {Latin!Paduan/g' main.ldx
	sed -i -e 's/indexentry {Peasant Latin/indexentry {Latin!Peasant/g' main.ldx
	sed -i -e 's/indexentry {Poetical Latin/indexentry {Latin!Poetical/g' main.ldx
	sed -i -e 's/indexentry {Roman|/indexentry {Latin!Roman|/g' main.ldx
	sed -i -e 's/indexentry {Castilian/indexentry {Spanish!Castilian/g' main.ldx
	sed -i -e 's/indexentry {Västergötland/indexentry {Swedish!Västergötland/g' main.ldx
	sed -i -e 's/indexentry {Protestant/indexentry {Protestant\(ism\)/g' main.sdx
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
	grep "^.author{" localmetadata.tex|grep -o "{.*"|egrep -o "[^{}]+" |sed 's/\\\(last\)\?and/"},{"name":"/g'>author
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
	git checkout master 
		
firstedition:
	git checkout gh-pages
	git pull 
	python getfirstedition.pdf `cat ID`
	git add first_edition.pdf 
	git commit -am 'provide first edition'
	git push origin gh-pages 
	git checkout master
	curl -X POST 'https://paperhive.org/api/document-items/remote?type=langsci&id='`cat ID`
	
	
proofreading.pdf:
	pdftk main.pdf multistamp prstamp.pdf output proofreading.pdf 
	
	
chop:  
	egrep -o "\{[0-9]+\}\{chapter\*\.[0-9]+\}" main.toc| egrep -o "[0-9]+\}\{chapter"|egrep -o [0-9]+ > cuts.txt
	egrep -o "\{chapter\}\{Index\}\{[0-9]+\}\{section\*\.[0-9]+\}" main.toc| grep -o "\..*"|egrep -o [0-9]+ >> cuts.txt
	bash chopchapters.sh `grep "mainmatter starts" main.log|grep -o "[0-9]*"`
	
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
	egrep -oh "[a-z] [A-Z]['a-zA-Z-]+" chapters/*tex| grep -o  [A-Z].* |sort -u >languagelist.txt


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


publish: googlebooks
	cp main.pdf final.pdf 
	cp main.pdf first_edition.pdf
	git checkout gh-pages
	git add first_edition.pdf 
	vim versions.json
	git commit -am 'provide first version'
	git push origin gh-pages
	git checkout master
	wikicite
# 	make bookblock modulo 4

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
