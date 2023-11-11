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
	sed -i 's/.*UNESCO.*//' main.adx
	sed -i 's/.*Report.*//' main.adx
	sed -i 's/\\MakeCapital//' main.adx
	#
	sed -i 's/active-voice|/active voice|/' main.sdx
	sed -i 's/Adjective|/adjective|/' main.sdx
	sed -i 's/adjunct nominal|/nominal adjunct|/' main.sdx
	sed -i 's/Adnominal adjective|/adnominal adjective|/' main.sdx
	sed -i 's/Adposition|/adposition|/' main.sdx
	sed -i 's/Adverb|/adverb|/' main.sdx
	sed -i 's/affective|/affective pronoun|/' main.sdx
	sed -i 's/Affective pronoun|/affective pronoun|/' main.sdx
	sed -i 's/allomorph|/allomorphy|/' main.sdx
	sed -i 's/ambitransitive|/ambitransitive|/' main.sdx
	sed -i 's/assimilating|/assimilation|/' main.sdx
	sed -i 's/atelic|/atelicity|/' main.sdx
	sed -i 's/Attributive adjective|/attributive adjective|/' main.sdx
	sed -i 's/auxiliary|/auxiliary verb|/' main.sdx
	sed -i 's/auxiliary-verb|/auxiliary verb|/' main.sdx
	sed -i 's/Bilabial|/bilabial|/' main.sdx
	sed -i 's/borrow|/borrowing|/' main.sdx
	sed -i 's/Cardinal numeral|/cardinal numeral|/' main.sdx
	sed -i 's/Causative|/causative|/' main.sdx
	sed -i 's/clause-chaining|/clause chaining|/' main.sdx
	sed -i 's/coalesce|/coalescence|/' main.sdx
	sed -i 's/cognate|/cognacy|/' main.sdx
	sed -i 's/colexified|/colexification|/' main.sdx
	sed -i 's/Complex onset|/complex onset|/' main.sdx
	sed -i 's/Compound|/compound|/' main.sdx
	sed -i 's/Conditional|/conditional|/' main.sdx
	sed -i 's/Consonant cluster|/consonant cluster|/' main.sdx
	sed -i 's/Content question|/content question|/' main.sdx
	sed -i 's/coordinate|/coordination|/' main.sdx
	sed -i 's/copular enclitic|/copular clitic|/' main.sdx
	sed -i 's/Dative|/dative|/' main.sdx
	sed -i 's/defective|/defective verb|/' main.sdx
	sed -i 's/degeminate|/degemination|/' main.sdx
	sed -i 's/deictic|/deixis|/' main.sdx
	sed -i 's/delete|/deletion|/' main.sdx
	sed -i 's/deleted|/deletion|/' main.sdx
	sed -i 's/deletes|/deletion|/' main.sdx
	sed -i 's/Demonstrative|/demonstrative|/' main.sdx
	sed -i 's/demote|/demotion|/' main.sdx
	sed -i 's/deontic|/deontic modality|/' main.sdx
	sed -i 's/Dependent clause|/dependent clause|/' main.sdx
	sed -i 's/Dependent marker|/dependent marker|/' main.sdx
	sed -i 's/dependent-marker|/dependent marker|/' main.sdx
	sed -i 's/dependent-marked|/dependent marker|/' main.sdx
	sed -i 's/Derivational morphology|/derivational morphology|/' main.sdx
	sed -i 's/derived|/derivation|/' main.sdx
	sed -i 's/derive|/derivation|/' main.sdx
	sed -i 's/Determiner|/determiner|/' main.sdx
	sed -i 's/detransitivizing|/detransitivizer|/' main.sdx
	sed -i 's/Direct discourse|/direct discourse|/' main.sdx
	sed -i 's/discontinuous|/discontinuous phrase|/' main.sdx
	sed -i 's/Distal|/distal|/' main.sdx
	sed -i 's/Disyllabic|/disyllabic|/' main.sdx
	sed -i 's/Dual|/dual|/' main.sdx
	sed -i 's/elide|/elision|/' main.sdx
	sed -i 's/elliptical|/ellipsis|/' main.sdx
	sed -i 's/endangered|/endangerment|/' main.sdx
	sed -i 's/epenthetic|/epenthesis|/' main.sdx
	sed -i 's/Farewell|/farewell|/' main.sdx
	sed -i 's/First person imperative|/first person imperative|/' main.sdx
	sed -i 's/fossilized|/fossilization|/' main.sdx
	sed -i 's/Geminate|/geminate|/' main.sdx
	sed -i 's/Gender|/gender|/' main.sdx
	sed -i 's/Glide|/glide|/' main.sdx
	sed -i 's/grammaticalizing|/grammaticalization|/' main.sdx
	sed -i 's/grammaticalized|/grammaticalization|/' main.sdx
	sed -i 's/Habitual|/habitual|/' main.sdx
	sed -i 's/homonymous|/homonymy|/' main.sdx
	sed -i 's/homophonous|/homophony|/' main.sdx
	sed -i 's/homophone|/homophony|/' main.sdx
	sed -i 's/homorganic|/homorganic consonant|/' main.sdx
	sed -i 's/iconic|/iconicity|/' main.sdx
	sed -i 's/Idiom|/idiom|/' main.sdx
	sed -i 's/Imperative|/imperative|/' main.sdx
	sed -i 's/Imperfective|/imperfective|/' main.sdx
	sed -i 's/in-situ|/in situ|/' main.sdx
	sed -i 's/Inclusory construction|/inclusory construction|/' main.sdx
	sed -i 's/Indefinite|/indefinite|/' main.sdx
	sed -i 's/inflect|/inflection|/' main.sdx
	sed -i 's/Interjection|/interjection|/' main.sdx
	sed -i 's/Interrogative word|/interrogative word|/' main.sdx
	sed -i 's/Intransitive|/intransitive|/' main.sdx
	sed -i 's/Irrealis|/irrealis|/' main.sdx
	sed -i 's/Irregular verb|/irregular verb|/' main.sdx
	sed -i 's/juxtaposed|/juxtaposition|/' main.sdx
	sed -i 's/juxtaposing|/juxtaposition|/' main.sdx
	sed -i 's/Kerám|/Keram River|/' main.sdx
	sed -i 's/Keram Black|/Keram Black River|/' main.sdx
	sed -i 's/lax|/lax vowel|/' main.sdx
	sed -i 's/Lexical|/lexicon|/' main.sdx
	sed -i 's/lexical|/lexicon|/' main.sdx
	sed -i 's/Loan|/loanword|/' main.sdx
	sed -i 's/loan|/loanword|/' main.sdx
	sed -i 's/Loanword|/loanword|/' main.sdx
	sed -i 's/medial-clause|/medial clause|/' main.sdx
	sed -i 's/Minimal pair|/minimal pair|/' main.sdx
	sed -i 's/modal|/mood|/' main.sdx
	sed -i 's/monophthongize|/monophthongization|/' main.sdx
	sed -i 's/Monosyllabic|/monosyllabic|/' main.sdx
	sed -i 's/morphological|/morphology|/' main.sdx
	sed -i 's/morphophonological|/morphophonology|/' main.sdx
	sed -i 's/morphosyntactic|/morphosyntax|/' main.sdx
	sed -i 's/Motion|/motion|/' main.sdx
	sed -i 's/Negation|/negation|/' main.sdx
	sed -i 's/Negative command|/negative command|/' main.sdx
	sed -i 's/Negative scope|/negative scope|/' main.sdx
	sed -i 's/Negator|/negator|/' main.sdx
	sed -i 's/nominalize|/nominalization|/' main.sdx
	sed -i 's/nominalizing|/nominalization|/' main.sdx
	sed -i 's/Non-verbal negation|/non-verbal negation|/' main.sdx
	sed -i 's/non-verbal negator|/non-verbal negation|/' main.sdx
	sed -i 's/Non-verbal predication|/non-verbal predication|/' main.sdx
	sed -i 's/non-verbal predicate|/non-verbal predication|/' main.sdx
	sed -i 's/Noun phrase|/noun phrase|/' main.sdx
	sed -i 's/Numeral|/numeral|/' main.sdx
	sed -i 's/object-marker|/object marker|/' main.sdx
	sed -i 's/Object marker|/object marker|/' main.sdx
	sed -i 's/object-marking|/object marking|/' main.sdx
	sed -i 's/Oblique|/oblique|/' main.sdx
	sed -i 's/oblique-marker|/oblique marker|/' main.sdx
	sed -i 's/obsolescent|/obsolescence|/' main.sdx
	sed -i 's/onomatopoetic|/onomatopoeia|/' main.sdx
	sed -i 's/Onomatopoetic|/onomatopoeia|/' main.sdx
	sed -i 's/orthographic|/orthography|/' main.sdx
	sed -i 's/palatalized|/palatalization|/' main.sdx
	sed -i 's/Palatalization|/palatalization|/' main.sdx
	sed -i 's/paratactic|/parataxis|/' main.sdx
	sed -i 's/parts of speech|/part of speech|/' main.sdx
	sed -i 's/Passive|/passive voice|/' main.sdx
	sed -i 's/passive|/passive voice|/' main.sdx
	sed -i 's/Passive-voice|/passive voice|/' main.sdx
	sed -i 's/passive-voice|/passive voice|/' main.sdx
	sed -i 's/penultimate|/penult|/' main.sdx
	sed -i 's/Perfective|/perfective|/' main.sdx
	sed -i 's/periphrases|/periphrasis|/' main.sdx
	sed -i 's/periphrastic|/periphrasis|/' main.sdx
	sed -i 's/phonetic|/phonetics|/' main.sdx
	sed -i 's/Phonetic|/phonetics|/' main.sdx
	sed -i 's/phonological|/phonology|/' main.sdx
	sed -i 's/Phonological|/phonology|/' main.sdx
	sed -i 's/phonotactic|/phonotactics|/' main.sdx
	sed -i 's/pluractional|/pluractionality|/' main.sdx
	sed -i 's/Polar question|/polar question|/' main.sdx
	sed -i 's/polite|/politeness|/' main.sdx
	sed -i 's/polysemous|/polysemy|/' main.sdx
	sed -i 's/polyseme|/polysemy|/' main.sdx
	sed -i 's/Possession|/possession|/' main.sdx
	sed -i 's/Possessive pronoun|/possessive pronoun|/' main.sdx
	sed -i 's/Possessor|/possessor|/' main.sdx
	sed -i 's/Postposition|/postposition|/' main.sdx
	sed -i 's/Postpositional phrase|/postpositional phrase|/' main.sdx
	sed -i 's/pragmatic|/pragmatics|/' main.sdx
	sed -i 's/Predicative adjective|/predicative adjective|/' main.sdx
	sed -i 's/prenasalize|/prenasalization|/' main.sdx
	sed -i 's/prenasalized|/prenasalization|/' main.sdx
	sed -i 's/Prohibition|/prohibition|/' main.sdx
	sed -i 's/prohibitive|/prohibitive marker|/' main.sdx
	sed -i 's/Pronoun|/pronoun|/' main.sdx
	sed -i 's/Proper noun|/proper noun|/' main.sdx
	sed -i 's/prothetic|/prothesis|/' main.sdx
	sed -i 's/Proximal|/proximal|/' main.sdx
	sed -i 's/Quasi-degemination|/quasi-degemination|/' main.sdx
	sed -i 's/Question|/question|/' main.sdx
	sed -i 's/reanalyzed|/reanalysis|/' main.sdx
	sed -i 's/reciprocal|/reciprocal pronoun|/' main.sdx
	sed -i 's/Reduplication|/reduplication|/' main.sdx
	sed -i 's/reflexive|/reflexive pronoun|/' main.sdx
	sed -i 's/Reflexive|/reflexive pronoun|/' main.sdx
	sed -i 's/Relative clause|/relative clause|/' main.sdx
	sed -i 's/relativize|/relativization|/' main.sdx
	sed -i 's/semantic|/semantics|/' main.sdx
	sed -i 's/Semantic extension|/semantic extension|/' main.sdx
	sed -i 's/Separable verb|/separable verb|/' main.sdx
	sed -i 's/Sepik|/Sepik River|/' main.sdx
	sed -i 's/Stress|/stress|/' main.sdx
	sed -i 's/Subject marker|/subject marker|/' main.sdx
	sed -i 's/suppletive|/suppletion|/' main.sdx
	sed -i 's/Swadesh|/Swadesh list|/' main.sdx
	sed -i 's/Swadesh List|/Swadesh list|/' main.sdx
	sed -i 's/{syllabic|/{syllabic consonant|/' main.sdx
	sed -i 's/synonymous|/synonymy|/' main.sdx
	sed -i 's/syntactic|/syntax|/' main.sdx
	sed -i 's/Tense|/tense|/' main.sdx
	sed -i 's/Third person imperative|/third person imperative|/' main.sdx
	sed -i 's/topic-marker|/topic marker|/' main.sdx
	sed -i 's/Transitive|/transitive|/' main.sdx
	sed -i 's/Trisyllabic|/trisyllabic|/' main.sdx
	sed -i 's/Velar|/velar|/' main.sdx
	sed -i 's/Verb phrase|/verb phrase|/' main.sdx
	sed -i 's/Verb stem|/verb stem|/' main.sdx
	sed -i 's/verbalized|/verbalization|/' main.sdx
	sed -i 's/verbalizing|/verbalization|/' main.sdx
	sed -i 's/Voiced|/voiced|/' main.sdx
	sed -i 's/word list|/wordlist|/' main.sdx
	sed -i 's/Yuat|/Yuat River|/' main.sdx
	#
	python3 fixindex.py
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
	
paperhive:  proofreading.pdf versions.json README.md
	(git commit -m 'new README' README.md && git push) || echo "README up to date" #this is needed for empty repositories, otherwise they cannot be branched
	git checkout gh-pages || git branch gh-pages; git checkout gh-pages
	git add proofreading.pdf versions.json
	git commit -m 'prepare for proofreading' proofreading.pdf versions.json
	git push origin gh-pages
	sleep 3
	curl -X POST 'https://paperhive.org/api/document-items/remote?type=langsci&id='`basename $(pwd)`
	git checkout main
	git commit -m 'new README' README.md
	git push
		
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
	*.glg *.glo *.gls *.wrd *.wdv *.xdv *.mw *.clr *.pgs \
	main.run.xml \
	chapters/*aux chapters/*~ chapters/*.bak chapters/*.backup \
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
	echo "Copyright: (c) "`date +"%Y"`", the authors." >> README.md
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
