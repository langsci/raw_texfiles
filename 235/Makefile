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
	sed -i -e 's/indexentry {Andalusi Romance/indexentry {Romance!Andalusi/g' main.ldx
	sed -i -e 's/indexentry {Western Aramaic/indexentry {Aramaic!Western/g' main.ldx
	sed -i -e 's/indexentry {Abu Dhabi/indexentry {Arabic!Abu Dhabi/g' main.ldx
	sed -i -e 's/indexentry {Algiers/indexentry {Arabic!Algiers/g' main.ldx
	sed -i -e 's/indexentry {American/indexentry {English!American/g' main.ldx
	sed -i -e 's/indexentry {Amman/indexentry {Arabic!Amman/g' main.ldx
	sed -i -e 's/indexentry {Anatolian/indexentry {Arabic!Anatolian/g' main.ldx
	sed -i -e 's/indexentry {Andalusi/indexentry {Arabic!Andalusi/g' main.ldx
	sed -i -e 's/indexentry {Antioch/indexentry {Domari!Antioch/g' main.ldx
	sed -i -e 's/indexentry {Aswan/indexentry {Arabic!Aswan/g' main.ldx
	sed -i -e 's/indexentry {Awjila/indexentry {Berber!Awjila/g' main.ldx
	sed -i -e 's/indexentry {Āzəḫ/indexentry {Arabic!Azeh@Āzəḫ/g' main.ldx
	sed -i -e 's/indexentry {Badini/indexentry {Kurdish!Kurmanji!Badini/g' main.ldx
	sed -i -e 's/indexentry {Baggara/indexentry {Arabic!Baggara/g' main.ldx
	sed -i -e 's/indexentry {Baghdadi/indexentry {Arabic!Baghdad/g' main.ldx
	sed -i -e 's/indexentry {Baghdad/indexentry {Arabic!Baghdad/g' main.ldx
	sed -i -e 's/indexentry {Bahraini/indexentry {Arabic!Bahrain/g' main.ldx
	sed -i -e 's/indexentry {Bahrain/indexentry {Arabic!Bahrain/g' main.ldx
	sed -i -e 's/indexentry {Baḫtiārī/indexentry {Persian!Baḫtiārī/g' main.ldx
	sed -i -e 's/indexentry {Bandarī/indexentry {Persian!Bandarī/g' main.ldx
	sed -i -e 's/indexentry {Bari Italian/indexentry {Italian!Bari dialect/g' main.ldx
	sed -i -e 's/indexentry {Basra/indexentry {Arabic!Basra/g' main.ldx
	sed -i -e 's/indexentry {Baṭḥari/indexentry {South Arabian!Modern \(MSAL\)!Baṭḥari/g' main.ldx
	sed -i -e 's/indexentry {Bedouin/indexentry {Arabic!Bedouin/g' main.ldx
	sed -i -e 's/indexentry {Beirut\/Damascus/indexentry {Domari!Beirut\/Damascus/g' main.ldx
	sed -i -e 's/indexentry {Beirut/indexentry {Arabic!Beirut/g' main.ldx
	sed -i -e 's/indexentry {Beni Snous/indexentry {Berber!Beni Snous/g' main.ldx
	sed -i -e 's/indexentry {Bongor/indexentry {Arabic!Bongor/g' main.ldx
	sed -i -e 's/indexentry {British/indexentry {English!British/g' main.ldx
	sed -i -e 's/indexentry {Buenos Aires Spanish/indexentry {Spanish!Buenos Aires/g' main.ldx
	sed -i -e 's/indexentry {Bukhari/indexentry {Arabic!Bukhari/g' main.ldx
	sed -i -e 's/indexentry {CA/indexentry {Arabic!Classical \(CA\)/g' main.ldx
	sed -i -e 's/indexentry {Cairene/indexentry {Arabic!Cairo/g' main.ldx
	sed -i -e 's/indexentry {Cairo/indexentry {Arabic!Cairo/g' main.ldx
	sed -i -e 's/indexentry {Casablanca/indexentry {Arabic!Casablanca/g' main.ldx
	sed -i -e 's/indexentry {Central Asian/indexentry {Arabic!Central Asian/g' main.ldx
	sed -i -e 's/indexentry {Central Kurdish/indexentry {Kurdish!Central/g' main.ldx
	sed -i -e 's/indexentry {Central Semitic/indexentry {Semitic!Central/g' main.ldx
	sed -i -e 's/indexentry {ChA/indexentry {Arabic!Chadian \(ChA\)/g' main.ldx
	sed -i -e 's/indexentry {Chadian/indexentry {Arabic!Chadian \(ChA\)/g' main.ldx
	sed -i -e 's/indexentry {Cilician/indexentry {Arabic!Cilician/g' main.ldx
	sed -i -e 's/indexentry {Cilicia/indexentry {Arabic!Cilician/g' main.ldx
	sed -i -e 's/indexentry {Classical Arabic/indexentry {Arabic!Classical \(CA\)/g' main.ldx
	sed -i -e 's/indexentry {Classical Latin/indexentry {Latin!Classical/g' main.ldx
	sed -i -e 's/indexentry {Classical Persian/indexentry {Persian!Classical/g' main.ldx
	sed -i -e 's/indexentry {Classical/indexentry {Arabic!Classical \(CA\)/g' main.ldx
	sed -i -e 's/indexentry {Cypriot Greek/indexentry {Greek!Cypriot/g' main.ldx
	sed -i -e 's/indexentry {Cypriot Maronite/indexentry {Arabic!Cypriot Maronite \(CyA\)/g' main.ldx
	sed -i -e 's/indexentry {Cypriot/indexentry {Greek!Cypriot/g' main.ldx
	sed -i -e 's/indexentry {Damascus/indexentry {Arabic!Damascus/g' main.ldx
	sed -i -e 's/indexentry {Daragözü/indexentry {Arabic!Daragözü/g' main.ldx
	sed -i -e 's/indexentry {Darī/indexentry {Persian!Darī/g' main.ldx
	sed -i -e 's/indexentry {Dhofar/indexentry {Arabic!Dhofar/g' main.ldx
	sed -i -e 's/indexentry {Dizfūlī/indexentry {Persian!Dizfūlī/g' main.ldx
	sed -i -e 's/indexentry {EA/indexentry {Arabic!Egyptian \(EA\)/g' main.ldx
	sed -i -e 's/indexentry {Early Modern English/indexentry {English!Early Modern/g' main.ldx
	sed -i -e 's/indexentry {Eastern Aramaic/indexentry {Aramaic!Eastern/g' main.ldx
	sed -i -e 's/indexentry {Eastern/indexentry {Arabic!Eastern/g' main.ldx
	sed -i -e 's/indexentry {Egyptian Arabic/indexentry {Arabic!Egyptian \(EA\)/g' main.ldx
	sed -i -e 's/indexentry {Egyptian/indexentry {Egyptian \(Ancient\)/g' main.ldx
	sed -i -e 's/indexentry {Fīnī/indexentry {Persian!Fīnī/g' main.ldx
	sed -i -e 's/indexentry {Gaza/indexentry {Arabic!Gaza/g' main.ldx
	sed -i -e 's/indexentry {GA/indexentry {Arabic!Gulf \(GA\)/g' main.ldx
	sed -i -e 's/indexentry {Gəʕəz/indexentry {Gəʕəz \(Gz.\)/g' main.ldx
	sed -i -e 's/indexentry {Ghamdi/indexentry {Arabic!Ghamdi/g' main.ldx
	sed -i -e 's/indexentry {Ghomara/indexentry {Berber!Ghomara/g' main.ldx
	sed -i -e 's/indexentry {Gulf Pidgin Arabic/indexentry {Arabic!Gulf Pidgin/g' main.ldx
	sed -i -e 's/indexentry {Gulf/indexentry {Arabic!Gulf \(GA\)/g' main.ldx
	sed -i -e 's/indexentry {Gz\./indexentry {Gəʕəz \(Gz.\)/g' main.ldx
	sed -i -e 's/indexentry {Hakitia/indexentry {Spanish!Hakitia/g' main.ldx
	sed -i -e 's/indexentry {Ḥapəs/indexentry {Arabic!Hapes@Ḥapəs/g' main.ldx
	sed -i -e 's/indexentry {Ḥarsūsi/indexentry {South Arabian!Modern \(MSAL\)!Harsusi@Ḥarsūsi/g' main.ldx
	sed -i -e 's/indexentry {Hasköy/indexentry {Arabic!Hasköy/g' main.ldx
	sed -i -e 's/indexentry {Ḥassāniyya/indexentry {Arabic!Hassaniyya@Ḥassāniyya/g' main.ldx
	sed -i -e 's/indexentry {Ḥiǧāzi/indexentry {Arabic!Higazi@Ḥiǧāzi/g' main.ldx
	sed -i -e 's/indexentry {IA/indexentry {Arabic!Iraqi \(IA\)/g' main.ldx
	sed -i -e 's/indexentry {Imperial Aramaic/indexentry {Aramaic!Imperial/g' main.ldx
	sed -i -e 's/indexentry {Imperial/indexentry {Aramaic!Imperial/g' main.ldx
	sed -i -e 's/indexentry {Iraqi/indexentry {Arabic!Iraqi \(IA\)/g' main.ldx
	sed -i -e 's/indexentry {Janaybi/indexentry {Arabic!Janaybi/g' main.ldx
	sed -i -e 's/indexentry {JA/indexentry {Arabic!Jordanian \(JA\)/g' main.ldx
	sed -i -e 's/indexentry {JBA/indexentry {Aramaic!Jewish Babylonian \(JBA\)/g' main.ldx
	sed -i -e 's/indexentry {Jebel Ansariye/indexentry {Arabic!Jebel Ansariye/g' main.ldx
	sed -i -e 's/indexentry {Jerusalem Domari/indexentry {Domari!Jerusalem/g' main.ldx
	sed -i -e 's/indexentry {Jerusalem/indexentry {Arabic!Jerusalem/g' main.ldx
	sed -i -e 's/indexentry {Jewish Babylonian Aramaic/indexentry {Aramaic!Jewish Babylonian \(JBA\)/g' main.ldx
	sed -i -e 's/indexentry {Jewish Babylonian/indexentry {Aramaic!Jewish Babylonian \(JBA\)/g' main.ldx
	sed -i -e 's/indexentry {Jordanian Domari/indexentry {Domari!Jordanian/g' main.ldx
	sed -i -e 's/indexentry {Jordanian Pidgin/indexentry {Arabic!Jordanian Pidgin/g' main.ldx
	sed -i -e 's/indexentry {Jordanian/indexentry {Arabic!Jordanian \(JA\)/g' main.ldx
	sed -i -e 's/indexentry {Juba/indexentry {Arabic!Juba/g' main.ldx
	sed -i -e 's/indexentry {Kabyle/indexentry {Berber!Kabyle/g' main.ldx
	sed -i -e 's/indexentry {Kenyan Kinubi/indexentry {Arabic!Kinubi!Kenyan/g' main.ldx
	sed -i -e 's/indexentry {Khuzestan/indexentry {Arabic!Khuzestan/g' main.ldx
	sed -i -e 's/indexentry {Kinderib/indexentry {Arabic!Kinderib/g' main.ldx
	sed -i -e 's/indexentry {Kinubi/indexentry {Arabic!Kinubi/g' main.ldx
	sed -i -e 's/indexentry {Kozluk–Sason–Muş/indexentry {Arabic!Kozluk–Sason–Muş/g' main.ldx
	sed -i -e 's/indexentry {Kozluk/indexentry {Arabic!Kozluk/g' main.ldx
	sed -i -e 's/indexentry {Kumzārī/indexentry {Kumzari/g' main.ldx
	sed -i -e 's/indexentry {Kurdistan/indexentry {Arabic!Kurdistan/g' main.ldx
	sed -i -e 's/indexentry {Kurmanji/indexentry {Kurdish!Kurmanji/g' main.ldx
	sed -i -e 's/indexentry {Lāristānī/indexentry {Persian!Lāristānī/g' main.ldx
	sed -i -e 's/indexentry {Late Latin/indexentry {Latin!Late \(LL\)/g' main.ldx
	sed -i -e 's/indexentry {Late/indexentry {Latin!Late \(LL\)/g' main.ldx
	sed -i -e 's/indexentry {LL/indexentry {Latin!Late \(LL\)/g' main.ldx
	sed -i -e 's/indexentry {Lat\./indexentry {Latin/g' main.ldx
	sed -i -e 's/indexentry {LA/indexentry {Arabic!Libyan \(LA\)/g' main.ldx
	sed -i -e 's/indexentry {Lebanese/indexentry {Arabic!Lebanese/g' main.ldx
	sed -i -e 's/indexentry {Levantine/indexentry {Arabic!Levantine/g' main.ldx
	sed -i -e 's/indexentry {Libyan/indexentry {Arabic!Libyan \(LA\)/g' main.ldx
	sed -i -e 's/indexentry {Lurī/indexentry {Persian!Lurī/g' main.ldx
	sed -i -e 's/indexentry {Maghrebi/indexentry {Arabic!Maghrebi/g' main.ldx
	sed -i -e 's/indexentry {Mahryōt/indexentry {South Arabian!Modern \(MSAL\)!Mehri!Mahriyōt/g' main.ldx
	sed -i -e 's/indexentry {Majorcan Catalan/indexentry {Catalan!Majorcan/g' main.ldx
	sed -i -e 's/indexentry {Majorcan Spanish/indexentry {Spanish!Majorcan/g' main.ldx
	sed -i -e 's/indexentry {Mali/indexentry {Arabic!Hassaniyya@Ḥassāniyya!Mali/g' main.ldx
	sed -i -e 's/indexentry {Maltese English/indexentry {English!Maltese/g' main.ldx
	sed -i -e 's/indexentry {Mardin/indexentry {Arabic!Mardin/g' main.ldx
	sed -i -e 's/indexentry {Marrakech/indexentry {Arabic!Marrakech/g' main.ldx
	sed -i -e 's/indexentry {MA/indexentry {Arabic!Moroccan \(MA\)/g' main.ldx
	sed -i -e 's/indexentry {MB/indexentry {Berber/g' main.ldx
	sed -i -e 's/indexentry {Mehreyyet/indexentry {South Arabian!Modern \(MSAL\)!Mehri!Mehreyyet/g' main.ldx
	sed -i -e 's/indexentry {Mehri/indexentry {South Arabian!Modern \(MSAL\)!Mehri/g' main.ldx
	sed -i -e 's/indexentry {Mesopotamian/indexentry {Arabic!Mesopotamian/g' main.ldx
	sed -i -e 's/indexentry {Middle English/indexentry {English!Middle/g' main.ldx
	sed -i -e 's/indexentry {Mlaḥso/indexentry {Aramaic!Mlaḥso/g' main.ldx
	sed -i -e 's/indexentry {Modern South Arabian/indexentry {South Arabian!Modern \(MSAL\)/g' main.ldx
	sed -i -e 's/indexentry {Modern Standard Persian/indexentry {Persian!Modern Standard \(MSP\)/g' main.ldx
	sed -i -e 's/indexentry {Moroccan Arabic/indexentry {Arabic!Moroccan \(MA\)/g' main.ldx
	sed -i -e 's/indexentry {Moroccan Berber/indexentry {Berber/g' main.ldx
	sed -i -e 's/indexentry {Moroccan/indexentry {Arabic!Moroccan \(MA\)/g' main.ldx
	sed -i -e 's/indexentry {Mosul/indexentry {Arabic!Mosul/g' main.ldx
	sed -i -e 's/indexentry {Mozabite/indexentry {Berber!Mozabite/g' main.ldx
	sed -i -e 's/indexentry {MSAL/indexentry {South Arabian!Modern \(MSAL\)/g' main.ldx
	sed -i -e 's/indexentry {Modern Standard/indexentry {Arabic!Modern Standard \(MSA\)/g' main.ldx
	sed -i -e 's/indexentry {Modern Standard Arabic/indexentry {Arabic!Modern Standard \(MSA\)/g' main.ldx
	sed -i -e 's/indexentry {MSA/indexentry {Arabic!Modern Standard \(MSA\)/g' main.ldx
	sed -i -e 's/indexentry {Mutki-Sason/indexentry {Arabic!Mutki-Sason/g' main.ldx
	sed -i -e 's/indexentry {Nabataean Aramaic/indexentry {Aramaic!Nabataean/g' main.ldx
	sed -i -e 's/indexentry {Nabataean/indexentry {Aramaic!Nabataean/g' main.ldx
	sed -i -e 's/indexentry {Najdi/indexentry {Arabic!Najdi/g' main.ldx
	sed -i -e 's/indexentry {NENA/indexentry {Neo-Aramaic!North-Eastern \(NENA\)/g' main.ldx
	sed -i -e 's/indexentry {Neo-Aramaic/indexentry {Aramaic!Neo-Aramaic/g' main.ldx
	sed -i -e 's/indexentry {New Persian/indexentry {Persian!New \(NewP\)/g' main.ldx
	sed -i -e 's/indexentry {NewP/indexentry {Persian!New \(NewP\)/g' main.ldx
	sed -i -e 's/indexentry {Nigerian/indexentry {Arabic!Nigerian/g' main.ldx
	sed -i -e 's/indexentry {N\. Kurd\./indexentry {Kurdish!Northern/g' main.ldx
	sed -i -e 's/indexentry {North-Eastern Neo-Aramaic/indexentry {Neo-Aramaic!North-Eastern \(NENA\)/g' main.ldx
	sed -i -e 's/indexentry {Northern Berber/indexentry {Berber!Northern/g' main.ldx
	sed -i -e 's/indexentry {Northern Kurdish/indexentry {Kurdish!Northern/g' main.ldx
	sed -i -e 's/indexentry {Northern/indexentry {Domari!Northern/g' main.ldx
	sed -i -e 's/indexentry {OA/indexentry {Arabic!Old/g' main.ldx
	sed -i -e 's/indexentry {Old Arabic/indexentry {Arabic!Old/g' main.ldx
	sed -i -e 's/indexentry {Old English/indexentry {English!Old/g' main.ldx
	sed -i -e 's/indexentry {Old French/indexentry {French!Old/g' main.ldx
	sed -i -e 's/indexentry {Old South Arabian/indexentry {South Arabian!Old/g' main.ldx
	sed -i -e 's/indexentry {Old Spanish/indexentry {Spanish!Old/g' main.ldx
	sed -i -e 's/indexentry {Old/indexentry {Arabic!Old/g' main.ldx
	sed -i -e 's/indexentry {Omani/indexentry {Arabic!Omani/g' main.ldx
	sed -i -e 's/indexentry {Oman/indexentry {Arabic!Omani/g' main.ldx
	sed -i -e 's/indexentry {Ottoman/indexentry {Turkish!Ottoman/g' main.ldx
	sed -i -e 's/indexentry {Palestine/indexentry {Arabic!Palestinian/g' main.ldx
	sed -i -e 's/indexentry {Palestinian/indexentry {Arabic!Palestinian/g' main.ldx
	sed -i -e 's/indexentry {Christian Palestinian Aramaic/indexentry {Aramaic!Christian Palestinian/g' main.ldx
	sed -i -e 's/indexentry {Diyarbakır/indexentry {Arabic!Diyarbakır/g' main.ldx
	sed -i -e 's/indexentry {Pidgin Madame/indexentry {Arabic!Pidgin Madame/g' main.ldx
	sed -i -e 's/indexentry {Post-Hilalian/indexentry {Arabic!Post-Hilalian/g' main.ldx
	sed -i -e 's/indexentry {Pre-Hilalian/indexentry {Arabic!Pre-Hilalian/g' main.ldx
	sed -i -e 's/indexentry {Romanian Pidgin/indexentry {Arabic!Romanian Pidgin/g' main.ldx
	sed -i -e 's/indexentry {Sana’a/indexentry {Arabic!Sana’a/g' main.ldx
	sed -i -e 's/indexentry {Sason/indexentry {Arabic!Sason/g' main.ldx
	sed -i -e 's/indexentry {SA/indexentry {Arabic!Sudanese \(SA\)/g' main.ldx
	sed -i -e 's/indexentry {Senhaja/indexentry {Berber!Senhaja/g' main.ldx
	sed -i -e 's/indexentry {Sfax/indexentry {Arabic!Sfax/g' main.ldx
	sed -i -e 's/indexentry {Shawiya/indexentry {Berber!Shawiya/g' main.ldx
	sed -i -e 's/indexentry {Śḥerɛt/indexentry {South Arabian!Modern \(MSAL\)!Sheret@Śḥerɛt/g' main.ldx
	sed -i -e 's/indexentry {Sicilian Arabic/indexentry {Arabic!Sicilian/g' main.ldx
	sed -i -e 's/indexentry {Šiḥḥī/indexentry {Arabic!Sihhi@Šiḥḥī/g' main.ldx
	sed -i -e 's/indexentry {Siirt/indexentry {Arabic!Siirt/g' main.ldx
	sed -i -e 's/indexentry {Siwa/indexentry {Berber!Siwa/g' main.ldx
	sed -i -e 's/indexentry {Siwi/indexentry {Berber!Siwa/g' main.ldx
	sed -i -e 's/indexentry {Soqoṭri/indexentry {South Arabian!Modern \(MSAL\)!Soqoṭri/g' main.ldx
	sed -i -e 's/indexentry {Sorani/indexentry {Kurdish!Sorani/g' main.ldx
	sed -i -e 's/indexentry {Soukhne/indexentry {Arabic!Soukhne/g' main.ldx
	sed -i -e 's/indexentry {Sousse/indexentry {Arabic!Sousse/g' main.ldx
	sed -i -e 's/indexentry {Southern/indexentry {Domari!Southern/g' main.ldx
	sed -i -e 's/indexentry {Standard Greek/indexentry {Greek!Standard/g' main.ldx
	sed -i -e 's/indexentry {Ancient Greek/indexentry {Greek!Ancient/g' main.ldx
	sed -i -e 's/indexentry {Standard/indexentry {Arabic!Modern Standard \(MSA\)/g' main.ldx
	sed -i -e 's/indexentry {Sudanese/indexentry {Arabic!Sudanese \(SA\)/g' main.ldx
	sed -i -e 's/indexentry {Sudanic pidgins/indexentry {Arabic!Sudanic pidgins/g' main.ldx
	sed -i -e 's/indexentry {Syriac/indexentry {Aramaic!Syriac/g' main.ldx
	sed -i -e 's/indexentry {Syr\./indexentry {Aramaic!Syriac/g' main.ldx
	sed -i -e 's/indexentry {Syrian/indexentry {Arabic!Syrian/g' main.ldx
	sed -i -e 's/indexentry {Tamazight/indexentry {Berber!Tamazight/g' main.ldx
	sed -i -e 's/indexentry {Tarifiyt/indexentry {Berber!Tarifiyt/g' main.ldx
	sed -i -e 's/indexentry {Tashelhiyt/indexentry {Berber!Tashelhiyt/g' main.ldx
	sed -i -e 's/indexentry {TA/indexentry {Arabic!Tunisian \(TA\)/g' main.ldx
	sed -i -e 's/indexentry {TB/indexentry {Berber!Tunisian \(TB\)/g' main.ldx
	sed -i -e 's/indexentry {Tillo Arabic/indexentry {Arabic!Tillo/g' main.ldx
	sed -i -e 's/indexentry {Tillo/indexentry {Arabic!Tillo/g' main.ldx
	sed -i -e 's/indexentry {Tlemcen/indexentry {Arabic!Tlemcen/g' main.ldx
	sed -i -e 's/indexentry {Tozeur/indexentry {Arabic!Tozeur/g' main.ldx
	sed -i -e 's/indexentry {Tr\./indexentry {Turkish/g' main.ldx
	sed -i -e 's/indexentry {Tuareg/indexentry {Berber!Tuareg/g' main.ldx
	sed -i -e 's/indexentry {Tunisian Arabic/indexentry {Arabic!Tunisian \(TA\)/g' main.ldx
	sed -i -e 's/indexentry {Tunisian Berber/indexentry {Berber!Tunisian \(TB\)/g' main.ldx
	sed -i -e 's/indexentry {Tunisian/indexentry {Arabic!Tunisian \(TA\)/g' main.ldx
	sed -i -e 's/indexentry {Tunis/indexentry {Arabic!Tunis/g' main.ldx
	sed -i -e 's/indexentry {Ṭuroyo/indexentry {Aramaic!Turoyo@Ṭuroyo/g' main.ldx
	sed -i -e 's/indexentry {Uzbekistan/indexentry {Arabic!Uzbekistan/g' main.ldx
	sed -i -e 's/indexentry {Vulgar/indexentry {Latin!Vulgar/g' main.ldx
	sed -i -e 's/indexentry {Western Neo-Aramaic/indexentry {Neo-Aramaic!Western/g' main.ldx
	sed -i -e 's/indexentry {Western Sudanic/indexentry {Arabic!Western Sudanic \(WSA\)/g' main.ldx
	sed -i -e 's/indexentry {Western Arabic/indexentry {Arabic!Western/g' main.ldx
	sed -i -e 's/indexentry {WSA/indexentry {Arabic!Western Sudanic \(WSA\)/g' main.ldx
	sed -i -e 's/indexentry {Western/indexentry {Arabic!Western/g' main.ldx
	sed -i -e 's/indexentry {Yemeni Arabic/indexentry {Arabic!Yemeni/g' main.ldx
	sed -i -e 's/indexentry {Yemeni/indexentry {Arabic!Yemeni/g' main.ldx
	sed -i -e 's/indexentry {Yemen/indexentry {Arabic!Yemeni/g' main.ldx
	sed -i -e 's/indexentry {Zenaga/indexentry {Berber!Zenaga \(Zen\.\)/g' main.ldx
	sed -i -e 's/indexentry {Zenati/indexentry {Berber!Zenati/g' main.ldx
	sed -i -e 's/indexentry {Zen\./indexentry {Berber!Zenaga \(Zen\.\)/g' main.ldx
	sed -i -e 's/indexentry {Zuwara/indexentry {Berber!Zuwara/g' main.ldx
	sed -i -e 's/indexentry {Zwara/indexentry {Berber!Zuwara/g' main.ldx
	sed -i -e 's/indexentry {Aleppo/indexentry {Arabic!Aleppo/g' main.ldx
	sed -i -e 's/indexentry {Aram\./indexentry {Aramaic/g' main.ldx
	sed -i -e 's/indexentry {Gk\./indexentry {Greek/g' main.ldx
	sed -i -e 's/indexentry {Kr\./indexentry {Kurdish/g' main.ldx
	sed -i -e 's/indexentry {Christian Bəḥzāni Aramaic/indexentry {Aramaic!Christian Bəḥzāni/g' main.ldx
	sed -i -e 's/indexentry {CSyr/indexentry {Aramaic!Syriac/g' main.ldx
	sed -i -e 's/indexentry {Ethio-Semitic/indexentry {Semitic!Ethiopian/g' main.ldx
	sed -i -e 's/indexentry {Hobyōt/indexentry {South Arabian!Modern \(MSAL\)!Hobyōt/g' main.ldx
	sed -i -e 's/indexentry {Koiné Greek/indexentry {Greek!Koiné/g' main.ldx
	sed -i -e 's/indexentry {Mandaic/indexentry {Aramaic!Mandaic/g' main.ldx
	sed -i -e 's/indexentry {Mecca/indexentry {Arabic!Mecca/g' main.ldx
	sed -i -e 's/indexentry {Middle Aramaic/indexentry {Aramaic!Middle/g' main.ldx
	sed -i -e 's/indexentry {MSP/indexentry {Persian!Modern Standard \(MSP\)/g' main.ldx
	sed -i -e 's/indexentry {Muş/indexentry {Arabic!Muş/g' main.ldx
	sed -i -e 's/indexentry {Neo-Aramaic/indexentry {Aramaic!Neo-Aramaic/g' main.ldx
	sed -i -e 's/indexentry {New Zealand/indexentry {English!New Zealand/g' main.ldx
	sed -i -e 's/indexentry {Northwest Semitic/indexentry {Semitic!Northwest/g' main.ldx
	sed -i -e 's/indexentry {Pers\./indexentry {Persian/g' main.ldx
	sed -i -e 's/indexentry {Sana’a/indexentry {Arabic!Sana’a/g' main.ldx
	sed -i -e '/indexentry {Arabic|hyperpage}/d' main.ldx
	sed -i -e '/indexentry {Arabic|hyperindexformat/d' main.ldx
	sed -i -e 's/indexentry {Arabic/indexentry {Arabic \(Ar\.\)/g' main.ldx
	sed -i -e 's/indexentry {Kurdish/indexentry {Kurdish \(Kr\.\)/g' main.ldx
	sed -i -e 's/indexentry {Persian/indexentry {Persian \(Pers\.\)/g' main.ldx
	sed -i -e 's/indexentry {Aramaic!Syriac/indexentry {Aramaic!Syriac \(Syr\.\)/g' main.ldx
	sed -i -e 's/indexentry {Aramaic/indexentry {Aramaic \(Aram\.\)/g' main.ldx
	sed -i -e 's/indexentry {Greek/indexentry {Greek \(Gk\.\)/g' main.ldx
	sed -i -e 's/indexentry {El-/indexentry {El/g' main.adx
	sed -i -e 's/indexentry {Al-/indexentry {Al/g' main.adx
	sed -i -e 's/indexentry {al-/indexentry {al/g' main.adx
	python3 fixindex.py
	mv mainmod.adx main.adx
	sed -i 's/hyperindexformat{\\\(infn {[0-9]*\)}/\1/' main.adx
	sed -i 's/hyperindexformat{\\\(infn {[0-9]*\)}/\1/' main.sdx # ordering of references to footnotes
	sed -i 's/hyperindexformat{\\\(infn {[0-9]*\)}/\1/' main.ldx
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
	python getfirstedition.py `cat ID`
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
