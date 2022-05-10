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
	sed -i -e 's/indexentry {additive enclitic/indexentry {enclitic!additive/g' main.sdx
	sed -i -e 's/indexentry {adverbial clause/indexentry {clause!adverbial/g' main.sdx
	sed -i -e 's/indexentry {affective verb/indexentry {verb!affective/g' main.sdx
	sed -i -e 's/indexentry {analytic verb form/indexentry {verb!analytic form/g' main.sdx
	sed -i -e 's/indexentry {backward control/indexentry {control!backward/g' main.sdx
	sed -i -e 's/indexentry {bivalent verbs/indexentry {verb!bivalent/g' main.sdx
	sed -i -e 's/indexentry {cardinal numerals/indexentry {numerals!cardinal/g' main.sdx
	sed -i -e 's/indexentry {causative construction/indexentry {construction!causative/g' main.sdx
	sed -i -e 's/indexentry {closest conjunct agreement/indexentry {agreement!closest conjunct/g' main.sdx
	sed -i -e 's/indexentry {cognition predicates/indexentry {predicate!cognition/g' main.sdx
	sed -i -e 's/indexentry {collective numerals/indexentry {numerals!collective/g' main.sdx
	sed -i -e 's/indexentry {comparative construction/indexentry {construction!comparative/g' main.sdx
	sed -i -e 's/indexentry {comparative constructions/indexentry {construction!comparative/g' main.sdx
	sed -i -e 's/indexentry {complement-taking predicate/indexentry {predicate!complement-taking/g' main.sdx
	sed -i -e 's/indexentry {compound verb/indexentry {verb!compound/g' main.sdx
	sed -i -e 's/indexentry {conditional clause/indexentry {clause!conditional/g' main.sdx
	sed -i -e 's/indexentry {consonants/indexentry {consonant/g' main.sdx
	sed -i -e 's/indexentry {content question/indexentry {questions!content/g' main.sdx
	sed -i -e 's/indexentry {degree adverb/indexentry {adverb!degree/g' main.sdx
	sed -i -e 's/indexentry {demonstrative pronoun/indexentry {pronoun!demonstrative/g' main.sdx
	sed -i -e 's/indexentry {demonstrative pronouns/indexentry {demonstrative pronoun/g' main.sdx
	sed -i -e 's/indexentry {deviant agreement/indexentry {agreement!deviant/g' main.sdx
	sed -i -e 's/indexentry {direct object/indexentry {object!direct/g' main.sdx
	sed -i -e 's/indexentry {distribution of consonants/indexentry {consonant!distribution of/g' main.sdx
	sed -i -e 's/indexentry {embedded question marker/indexentry {questions!embedded marker/g' main.sdx
	sed -i -e 's/indexentry {equative constructions/indexentry {construction!equative/g' main.sdx
	sed -i -e 's/indexentry {existential copula/indexentry {copula!existential/g' main.sdx
	sed -i -e 's/indexentry {experiential past/indexentry {past!experiential/g' main.sdx
	sed -i -e 's/indexentry {forward control/indexentry {control!forward/g' main.sdx
	sed -i -e 's/indexentry {geminate consonant/indexentry {consonant!geminate/g' main.sdx
	sed -i -e 's/indexentry {glide insertion/indexentry {insertion!glide/g' main.sdx
	sed -i -e 's/indexentry {glottal stop insertion/indexentry {insertion!glottal stop/g' main.sdx
	sed -i -e 's/indexentry {group numeral/indexentry {numerals!group/g' main.sdx
	sed -i -e 's/indexentry {habitual past/indexentry {past!habitual/g' main.sdx
	sed -i -e 's/indexentry {imperfective aspect/indexentry {aspect!imperfective/g' main.sdx
	sed -i -e 's/indexentry {imperfective converb/indexentry {converb!imperfective/g' main.sdx
	sed -i -e 's/indexentry {indefinite pronoun/indexentry {pronoun!indefinite/g' main.sdx
	sed -i -e 's/indexentry {indirect object/indexentry {object!indirect/g' main.sdx
	sed -i -e 's/indexentry {interrogative clause/indexentry {clause!interrogative/g' main.sdx
	sed -i -e 's/indexentry {intransitive verb/indexentry {verb!intransitive/g' main.sdx
	sed -i -e 's/indexentry {involuntary agent construction/indexentry {construction!involuntary agent/g' main.sdx
	sed -i -e 's/indexentry {labile verbs/indexentry {verb!labile/g' main.sdx
	sed -i -e 's/indexentry {light verb/indexentry {verb!light/g' main.sdx
	sed -i -e 's/indexentry {local reflexivization/indexentry {reflexivization!local/g' main.sdx
	sed -i -e 's/indexentry {locational copula/indexentry {copula!locational/g' main.sdx
	sed -i -e 's/indexentry {locative participle/indexentry {participle!locative/g' main.sdx
	sed -i -e 's/indexentry {locative participle/indexentry {participle!locative/g' main.sdx
	sed -i -e 's/indexentry {long-distance reflexivization/indexentry {reflexivization!long-distance/g' main.sdx
	sed -i -e 's/indexentry {manipulative verbs/indexentry {verb!manipulative/g' main.sdx
	sed -i -e 's/indexentry {manner adverbs/indexentry {adverb!manner/g' main.sdx
	sed -i -e 's/indexentry {modal enclitic/indexentry {enclitic!modal/g' main.sdx
	sed -i -e 's/indexentry {modal participle/indexentry {participle!modal/g' main.sdx
	sed -i -e 's/indexentry {modal verb/indexentry {verb!modal/g' main.sdx
	sed -i -e 's/indexentry {monovalent verb/indexentry {verb!monovalent/g' main.sdx
	sed -i -e 's/indexentry {multiplicative numerals/indexentry {numerals!multiplicative/g' main.sdx
	sed -i -e 's/indexentry {ordinal numerals/indexentry {numerals!ordinal/g' main.sdx
	sed -i -e 's/indexentry {partitive construction/indexentry {construction!partitive/g' main.sdx
	sed -i -e 's/indexentry {past tense/indexentry {tense!past/g' main.sdx
	sed -i -e 's/indexentry {perfective aspect/indexentry {aspect!perfective/g' main.sdx
	sed -i -e 's/indexentry {perfective converb/indexentry {converb!perfective/g' main.sdx
	sed -i -e 's/indexentry {periphrastic verb form/indexentry {verb!periphrastic form/g' main.sdx
	sed -i -e 's/indexentry {person agreement/indexentry {agreement!person/g' main.sdx
	sed -i -e 's/indexentry {phasal verbs/indexentry {verb!phasal/g' main.sdx
	sed -i -e 's/indexentry {present tense/indexentry {tense!present/g' main.sdx
	sed -i -e 's/indexentry {preterite participle/indexentry {participle!preterite/g' main.sdx
	sed -i -e 's/indexentry {purposive clauses/indexentry {clause!purposive/g' main.sdx
	sed -i -e 's/indexentry {reciprocal constructions/indexentry {construction!reciprocal/g' main.sdx
	sed -i -e 's/indexentry {reciprocal pronoun/indexentry {pronoun!reciprocal/g' main.sdx
	sed -i -e 's/indexentry {reflexive construction/indexentry {construction!reflexive/g' main.sdx
	sed -i -e 's/indexentry {reflexive pronoun/indexentry {pronoun!reflexive/g' main.sdx
	sed -i -e 's/indexentry {relative clause/indexentry {clause!relative/g' main.sdx
	sed -i -e 's/indexentry {simple clause/indexentry {clause!simple/g' main.sdx
	sed -i -e 's/indexentry {spatial adverb/indexentry {adverb!spatial/g' main.sdx
	sed -i -e 's/indexentry {tag question/indexentry {questions!tag/g' main.sdx
	sed -i -e 's/indexentry {temporal adverb/indexentry {adverb!temporal/g' main.sdx
	sed -i -e 's/indexentry {temporal enclitic/indexentry {enclitic!temporal/g' main.sdx
	sed -i -e 's/indexentry {tense consonant/indexentry {consonant!tense/g' main.sdx
	sed -i -e 's/indexentry {three-place verbs/indexentry {verb!three-place/g' main.sdx
	sed -i -e 's/indexentry {transitive verb/indexentry {verb!transitive/g' main.sdx
	sed -i -e 's/indexentry {trivalent verb/indexentry {verb!trivalent/g' main.sdx
	sed -i -e 's/indexentry {two-place verb/indexentry {verb!two-place/g' main.sdx
	sed -i -e 's/indexentry {utterance verb/indexentry {verb!utterance/g' main.sdx

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
	grep "^.BookDOI{" localmetadata.tex|grep -o "{.*"|egrep -o "[^{}]+">doi
	grep "^.author{" localmetadata.tex|grep -o "{.*"|egrep -o "[^{}]+" |sed 's/\\\(last\)\?and/"},{"name":"/g'>author
	echo '{"versions": [{"versiontype": "proofreading",' >versions.json
	echo -n '		"title": "' >>versions.json
	echo -n `cat title` >> versions.json
	echo  '",' >> versions.json
	echo -n  '		"authors": [{"name": "'>> versions.json
	echo -n `cat author` >> versions.json 
	echo  '"}],' >> versions.json 
	echo  '	"license": "CC-BY-4.0",'>> versions.json
	echo -n '	"DOI": "'>> versions.json
	echo -n `cat doi` >> versions.json	
	echo '",' >> versions.json
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
	egrep -oh "[a-z] [A-Z][a-z]+" chapters/*tex| grep -o  [A-Z].* |sort -u >languagelist.txt


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
