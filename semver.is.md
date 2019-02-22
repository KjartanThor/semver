Merkingartengd útgáfunúmer 2.0.0
================================

Samantekt
---------

Með útgáfunúmer MAJOR.MINOR.PATCH, hækkar:

1. MAJOR útgáfu þegar þú gerir ósamhæfðar viðmóts breytingar,
1. MINOR útgáfu þegar þú bætir virkni við á afturhæfan máta, og
1. PATCH útgáfu þegar þú gerir villuleiðréttingar á afturhæfan máta.

Aðrar merkingar fyrir for-útgáfur og smíðalýsigögn eru mögulegar sem viðbætur 
við MAJOR.MINOR.PATCH sniðið.

Inngangur
---------

Í heimi hugbúnaðargerðar er staður sem kallast "ákvæðisvíti." Því umfangsmeira
sem kerfið verður og því fleiri pakkar sem eru samþættir við hugbúnaðinn, því 
líklegra er að þú upplifir þig, dag einn, í þessum pitti vonleysis.

Í kerfum með mörgum ákvæðum getur framleiðsla á nýrri útgáfum pakka fljótt orðið
eins og martröð. Ef ákvæðisskilgreiningarnar eru of þröngar, er hætta á að
útgáfulæsingu (í þeirri stöðu er ómögulegt að uppfæra pakka án þess að gefa
út nýjar útgáfur af öllum ákvæðispökkum). Ef ákvæði eru of lauslega skilgreind, 
kemur óhjákvæmilega að útgáfufjölveri (samhæfni talin vera við fleiri framtíðar
útgáfur en er raunhæft). Ákvæðisvíti er þegar útgáfu fjölveri og /eða 
útgáfulæsing hindra auðvelda og örugga framþróun verkefnis.

Til að leysa þetta vandamál eru lagðar til reglur og kröfur sem stýra því 
hvernig útgáfunúmer eru ákvörðuð og þeim breytt. Þessar reglur eru byggðar á 
þekktum, algengum aðferðum í bæði opinni og lokaðri hugbúnaðargerð, en 
takmarkast ekki nauðsynlega af þeim. Til þess að kerfið virki, þarf fyrst að 
skilgreina notfrjáls forritunarskil. Skilgreiningin getur verið í skjölun eða 
framfylgt í kódanum. Óháð skilgreiningu er mikilvægt að forritunarskilin sé 
nákvæm og skýr. Þegar notfrjáls forritunarskil hafa verið skilgreind, eru 
breytingar á þeim gefnar til kynna með ákveðnum hækkunum á útgáfunúmerum.
Skoðum útgáfu sniðið X.Y.Z (Major.Minor.Patch). Villuleiðréttingar sem ekki 
breyta forritunarskilunum hækka patch hlutann, afturhæfar breytingar og viðbætur
á forritunarskilunum hækka minor hlutann og óafturhæfar breytingar á 
forritunarskilum hækka major hlutann.

Þetta kerfi er kallað "merkingartengd útgáfunúmer." Með þessari aðferð gefa 
útgáfunúmer og hvernig þau breytast til kynna hvernig kódinn hefur 
breyst frá einni útgáfu til annarrar.


Skilgreining merkingartengdra útgáfunúmera (SemVer)
---------------------------------------------------

Lykilorðin "VERÐUR" (MUST), "MÁ EKKI" (MUST NOT), "NAUÐSYNLEGT" (REQUIRED), 
"SKAL" (SHALL), "SKAL EKKI" (SHALL NOT), "ÆTTI" (SHOULD), "ÆTTI EKKI" (SHOULD NOT),
"ÆSKILEGT" (RECOMMENDED), "GÆTI" (MAY), "VALFRJÁLST" (OPTIONAL) í þessu skjali 
skulu túlkuð á sama hátt og lýst er í [RFC 2119](http://tools.ietf.org/html/rfc2119).

1. Hugbúnaður sem notar merkingartengd útgáfunúmer VERÐUR að skilgreina notfrjáls
forritunarskil. Þessi forritunarskil geta verið skilgreind í kódanum eða fundist
eingöngu í skjölun. Hvernig sem þau eru útfærð, ÆTTU þau að vera nákvæm og víðtæk.

1. Venjulegt útgáfunúmer VERÐUR að vera á sniðinu X.Y.Z	hvar X, Y og Z eru 
heiltölur sem ekki eru neikvæðar og MEGA EKKI innihalda leiðandi núll. X er 
major útgáfan, Y er minor útgáfan og Z er patch útgáfan.
Hvert stak VERÐUR að hækka tölulega. Til dæmis: 1.9.0 -> 1.10.0 -> 1.11.0.

1. Þegar pakki með útgáfunúmeri hefur verið gefinn út MÁ EKKI breyta innihaldinu.
Allar breytingar VERÐA að vera gefnar út sem ný útgáfa.

1. Major útgáfa núll (0.y.z) er fyrir frumþróun. Allt GETUR breyst á hvaða tíma
sem er. Notfrjáls forritunarskil ÆTTU EKKI að teljast stöðug.

1. Útgáfa 1.0.0 skilgreinir notfrjáls forritunarskil. Hvernig útgáfunúmerið
hækkar eftir þessa útgáfu er háð þessum notfrjálsu forritunarskilum og hvernig
þau breytast.

1. Patch útgáfan Z (x.y.Z | x > 0) VERÐUR að hækka ef eingöngu afturhæfum
villuleiðréttingum hefur verið bætt við. Villuleiðrétting er skilgreind sem
innvær breyting sem lagfærir ranga hegðun.

1. Minor útgáfan Y (x.Y.z | x > 0) VERÐUR að hækka ef nýrri, afturhæfri virkni
hefur verið bætt við notfrjálsu forritunarskilin. Það VERÐUR að hækka ef einhver
virkni notfrjálsra forritunarskila er merkt sem "deprecated". Það GÆTI hækkað 
ef talsverðri nýrri virkni eða endurbótum er bætt í lokaðan kóda. Það GÆTI 
innifalið breytingar á patch stigi. Patch útgáfuna VERÐUR að setja aftur í 0
þegar minor útgáfan er hækkuð.

1. Major útgáfan X (X.y.z | X > 0) VERÐUR að hækka ef einhverri óafturhæfri virkni
er bætt í notfrjálsa forritunarviðmótið. Það GETUR einnig innifalið breytingar á 
minor og patch stigi. Patch og minor útgáfur VERÐUR að setja aftur á 0 þegar 
major útgáfa er hækkuð.

1. Forútgáfu má tákna með því að skeyta bandstriki og röð einkenna aðgreind 
með punkti strax á eftir patch útgáfunni. Einkenni VERÐA að vera samsett 
eingöngu með ASCII bók- og tölustöfum ásamt bandstriki [0-9A-Za-z-]. Einkenni 
MEGA EKKI vera tóm. Töluleg einkenni MEGA EKKI innihalda leiðandi núll. 
Forútgáfunúmer hafa lægri forgang en hefbundin útgáfunúmer. Forútgáfunúmer gefur 
til kynna að útgáfan sé óstöðug og fullnægi ekki samhæfingarkröfum sem gerðar 
eru til samsvarandi hefðbundinnar útgáfu. Dæmi: 1.0.0-alpha, 1.0.0-alpha.1, 
1.0.0-0.3.7, 1.0.0-x.7.z.92.

1. Lýsigögn úr smíði MÁ merkja með því að skeyta við plús merki og röð einkenna
aðgreindum með punkti strax á eftir patch eða forútgáfunúmeri. Einkenni VERÐA að
vera samsett með ASCII bók- og tölustöfum og bandstriki [0-9A-Za-z-]. Einkenni
MEGA EKKI vera tóm. Lýsigögn úr smíði VERÐUR að hunsa þegar röð útgáfunúmera er
ákvörðuð. Þannig verða tvær útgáfur sem eingöngu munar á lýsigögnum úr smíði með 
sama forgang. Dæmi: 1.0.0-alpha+001, 1.0.0+20130313144700, 
1.0.0-beta+exp.sha.5114f85

1. Forgangur vísar til þess hvernig útgáfur eru bornar saman við hverja aðra 
þegar þeim er raðað. Forgangur VERÐUR að vera reiknaður með því að slíta sundur
útgáfunúmerið í major, minor, patch og forútgáfu einkenni í þeirri röð (lýsigögn
úr smíði hafa engin áhrif á forgang). Forgangur er ákvarðaður út frá fyrsta mismun
sem finnst við samanburð þessara einkenna frá vinstri til hægri eins og hér á
eftir: major, minor og patch útgáfur eru alltaf bornar saman sem heiltölur. 
Dæmi: 1.0.0 < 2.0.0 < 2.1.0 < 2.1.1. Þegar major, minor og patch eru jöfn hefur
forútgáfa lægri forgang en venjuleg útgáfa. Dæmi: 1.0.0-alpha < 1.0.0. Forgangur
tveggja forúgáfa með sömu major, minor og patch útgáfur VERÐUR að vera ákvarðaður
með samanburði hvers einkennis aðgreinds með punkti frá vinstri til hægri þar 
munur finnst eins og hér á eftir: einkenni samsett eingöngu með tölum eru borin 
saman sem talnagildi og einkenni með bók- og tölustöfum eru borin saman sem 
strengir í ASCII röðun. Töluleg einkenni hafa alltaf lægri forgang en ótöluleg
einkenni. Stærra sett forútgáfu einkenna hefur hærri forgang en minna sett, ef 
öll fyrri einkenni eru jöfn. Dæmi: 1.0.0-alpha < 1.0.0-alpha.1 < 1.0.0-alpha.beta
< 1.0.0-beta < 1.0.0-beta.2 < 1.0.0-beta.11 < 1.0.0-rc.1 < 1.0.0. 

Backus–Naur mállýsing fyrir gild SemVer útgáfunúmer
---------------------------------------------------

    <gilt semver> ::= <útgáfu kjarni>
                     | <útgáfu kjarni> "-" <forútgáfa>
                     | <útgáfu kjarni> "+" <smíði>
                     | <útgáfu kjarni> "-" <forútgáfa> "+" <smíði>

    <útgáfu kjarni> ::= <major> "." <minor> "." <patch>

    <major> ::= <tölulegt einkenni>

    <minor> ::= <tölulegt einkenni>

    <patch> ::= <tölulegt einkenni>

    <forútgáfa> ::= <forútgáfu einkenni aðgreind með punkti>

    <forútgáfu einkenni aðgreind með punkti> ::= <forútgáfu einkenni>
                                              | <forútgáfu einkenni> "." <forútgáfueinkenni aðgreind með punkti>

    <smíði> ::= <smíðis einkenni aðgreind með punkti>

    <smíðis einkenni aðgreind með punkti> ::= <smíðis einkenni>
                                        | <smíðis einkenni> "." <smíðiseinkenni aðgreind með punkti>

    <forútgáfu einkenni> ::= <ritstafa einkenni>
                               | <tölulegt einkenni>

    <smíðis einkenni> ::= <ritstafa einkenni>
                         | <tölur>

    <ritstafa einkenni> ::= <ekki-tala>
                                | <ekki-tala> <einkennis stafir>
                                | <einkennis stafir> <ekki-tala>
                                | <einkennis stafir> <ekki-tala> <einkennis stafir>

    <tölulegt einkenni> ::= "0"
                           | <jákvæð tala>
                           | <jákvæð tala> <tölur>

    <einkennis stafir> ::= <einkennis stafur>
                              | <einkennis stafur> <einkennis stafir>

    <einkennis stafur> ::= <tala>
                             | <ekki-tala>

    <ekki-tala> ::= <bókstafur>
                  | "-"

    <tölur> ::= <tala>
               | <tala> <tölur>

    <tala> ::= "0"
              | <jákvæð tala>

    <jákvæð tala> ::= "1" | "2" | "3" | "4" | "5" | "6" | "7" | "8" | "9"

    <bókstafur> ::= "A" | "B" | "C" | "D" | "E" | "F" | "G" | "H" | "I" | "J"
               | "K" | "L" | "M" | "N" | "O" | "P" | "Q" | "R" | "S" | "T"
               | "U" | "V" | "W" | "X" | "Y" | "Z" | "a" | "b" | "c" | "d"
               | "e" | "f" | "g" | "h" | "i" | "j" | "k" | "l" | "m" | "n"
               | "o" | "p" | "q" | "r" | "s" | "t" | "u" | "v" | "w" | "x"
               | "y" | "z"


Af hverju að nota merkingartengd útgáfunúmer?
---------------------------------------------

Þetta er ekki ný eða byltingarkennd hugmynd. Í raun eru mestar líkur á að þú
gerir eitthvað í líkingu við þetta nú þegar. Vandinn er að "í líkingu" er ekki 
nægilega gott. Ef ekki er farið eftir formlegri skilgreiningu eru útgáfunúmer
ónothæf við umsýslu ákvæða. Með því að gefa hugmyndunum að ofan nafn og skýra
skilgreiningu verður auðveldara að gefa notendum hugbúnaðarins tilætlanir þínar
til kynna. Þegar tilætlanir eru skýrar, sveigjanlegar (en ekki of sveigjanlegar)
er loksins hægt að skilgreina ákvæði.

Með einföldu dæmi er hægt að sýna fram á hvernig ákvæðisvíti tilheyra sögunni 
með notkun merkingartengdra útgáfunúmera. Tökum dæmi af safni með nafnið 
"Brunabíll." Safnið þarfnast pakka með merkingartengdu útgáfunúmeri sem heitir
"Stigi." Þegar Brunabíll er búinn til er Stigi í útgáfunni 3.1.0. Þar sem 
Brunabíll notar virkni sem var bætt við í útgáfu 3.1.0 er óhætt að skilgreina 
ákvæðið á Stiga sem stærra eða jafnt og 3.1.0 en lægra en 4.0.0. Þegar útgáfur
3.1.1 og 3.2.0 af Stiga verða tiltækar er óhætt að bæta þeim í pakkaumsýslukerfið
án þess að hafa áhyggjur af að þeir séu ósamhæfðir við annan ákvæðishugbúnað.

Sem ábyrgur forritari þarftu eðli málsins samkvæmt að ganga úr skugga um að
uppfærslur pakka virki eins og gefið er til kynna. Veruleikinn er subbulegur,
það er ekkert við því að gera annað en að vera á varðbergi. Það sem þú getur 
gert er að nota merkingartengd útgáfunúmer til að fá skynsamlega leið til að
sýsla með og uppfæra pakka án þess að þurfa að gefa út nýjar útgáfur af pökkum,
þannig sparast tími og vandræði.

Ef þetta hljómar æskilegt, er allt sem þú þarft til að hefja notkun á 
merkingartengdum útgáfunúmerum að lýsa því yfir og fylgja reglunum. Settu hlekk
á þetta vefsvæði í README skránna svo aðrir þekki reglurnar og þær gagnist þeim.


Algengar spurningar
-------------------

### Hvernig á ég að meðhöndla breytingar í 0.y.z þróunarfasanum í upphafi?

Einfaldast er að hefja þróunina í útgáfu 0.1.0 og hækka svo minor útgáfuna
með hverri útgáfu eftir það.

### Hvernig veit ég að nú sé rétt að gefa út 1.0.0?

Ef hugbúnaðurinn er notaður í raunumhverfi ætti hann að öllum líkindum að vera
kominn í útgáfu 1.0.0. Ef þú ert með stöðug notfrjáls forritunarskil sem notendur
eru farnir að reiða sig á, ættirðu að vera í útgáfu 1.0.0. Ef þú ert farinn að 
hafa áhyggjur af afturhæfi, ættirðu sennilega að vera í útgáfu 1.0.0.

### Dregur þetta ekki úr örri þróun og þéttum ítrunum?

Major útgáfa núll snýst öll um öra þróun. ef þú ert að breyta forritunarskilunum
á hverjum degi ættirðu annað hvort að vera enn í útgáfu 0.y.z eða á sérstakri
þróunargrein að vinna að næstu major útgáfu.

### Ef það er minnsta óafturhæfa breyting á notfrjálsu forritunarskilunum krefst það hækkunnar á major útgáfu, enda ég þá ekki í útgáfu 42.0.0 mjög fljótt?

Þetta er spurningin um ábyrga þróun og forsjálni. Allar óafturhæfar breytingar
ætti að ígrunda vel sér í lagi í hugbúnaði sem margir eru með ákvæði á. Kostnaður
við uppfærslur getur verið töluverður. Að verða að hækka major útgáfu þegar þú 
gefur út óafturhæfar breytingar þýðir að þú þarft að ígrunda vel hvaða áhrif 
breytingarnar koma til með að hafa og meta hlutfallið milli kostnaðar og kosta
við breytingarnar.

### Það er of mikil vinna að skjala allt notfrjálsa forritunarviðmótið!

Það er á þína ábyrgð sem faglegur forritari að skjala á fullnægjandi máta þann
hugbúnað sem ætlaður er til nota af öðrum. Stjórnun flækjustigs hugbúnaðar er 
afar mikilvægur hluti af að halda verkefni skilvirku og það er afar erfitt ef
enginn veit hvernig skal nota hugbúnaðinn þinn eða hvaða föll er óhætt að kalla í.
Til lengri tíma litið geta vel skilgreind forritunarskil ásamt merkingartengdum 
útgáfunúmerum heldur öllum og öllu keyrandi mjúklega.

### Hvað á ég að gera ef ég gef óvart út óafturhæfar breytingar sem minor útgáfu?

Um leið og þú áttar þig á að þú hefur brotið skilgreiningu merkingartengdra
útgáfunúmera skaltu lagfæra vandamálið og gefa út nýja minor útgáfu sem 
leiðréttir vandamálið og endurvekur afturhæfi. Jafnvel í þessum aðstæðum er
ekki í lagi að breyta áður útgefinni útgáfu. Ef við á skal skjala brotnu 
útgáfuna þannig og upplýsa notendur um vandamálið svo þeir séu meðvitaðir um
óæskilegu útgáfuna.

### Hvað á ég að gera ef ég uppfæri mitt eigið ákvæði án þess að breyta notfrjálsa forritunarviðmótinu?

Þessi breyting telst afturhæf þar sem hún hefur ekki áhrif á notfrjálsa 
forritunarviðmótið. Hugbúnaður sem hefur nákvæmlegea sömu ákvæðu og pakkinn þinn
ættu að hafa sínar eigin ákvæðisskilgreiningar og höfundur þeirra mun taka eftir
árekstrum. Hvort um er að ræða patch eða minor stigs breyting veltur á því hvort
ákvæði var uppfært til að lagfæra villu eða til að bæta við nýrri virkni. Oftast
má gera ráð fyrir nýjum kóda í seinna tilvikinu, í því tilviki er augljóslega
um hækkun á minor útgáfu.

### Hvað ef ég breyti óvart notfrjálsa notendaviðmótinu á máta sem er ekki í samræmi við breytinguna á útgáfunúmerinu (t.d. kódinn breytist á óafturhæfan máta í patch útgáfu)
### What if I inadvertently alter the public API in a way that is not compliant with the version number change (i.e. the code incorrectly introduces a major breaking change in a patch release)

Notaðu eigin dómgreind. Ef mjög margir verða fyrir miklum áhrifum af breytingu
til baka í það sem notfrjálsa forritunarviðmótið á að vera, þá gæti verið 
heppilegast að gefa út major útgáfu, jafnvel þó að lagfæring gæti verið skoðuð
sem patch útgáfa. Hafið í huga að merkingartengd útgáfunúmer snúast um að 
gefa til kynna merkingu þegar útgáfunúmer breytast. Ef breytingarnar eru 
mikilvægar fyrir notendurnar, þá notarðu útgáfunúmer til að upplýsa þá.

### Hvernig meðhöndla ég "depricate" merkingar á virkni?

"Depricate" merkingar á útgefinni virkni er eðlilegur hluti af hugbúnaðarþróun
og er oft nauðsynlegt við framþróun verkefnis. Þegar þú "depricate" merkir hluta
af notfrjálsa forritunarviðmótinu ættirðu að gera tvo hluti: (1) uppfæra 
skjölunina til að láta notendur vita, (2) gefa út minor útgáfu með "depricate" 
merkinguna á sínum stað. Áður en þú líkur við að fjarljægja virknina í nýrri
major útgáfu ætti alltaf að vera ein minor útgáfa sem inniheldur "depricate" 
merkinguna svo notendur geti auðveldlega tengst nýja forritunarviðmótinu.

### Eru lengdartakmarkanir á útgáfunúmers strengnum í SemVer?

Nei, notið eigin dómgreind. 255 stafa útgáfunúmer er til dæmis að öllum líkindum
of mikið. Einnig gætu einhver kerfið verið með sýnar eigin takmarkanir á lengd 
strengsins.

### Er "v1.2.3" merkingartengt útgáfunúmer?

Nei "v1.2.3" er ekki merkingartengt útgáfunúmer. Hins vegar er algengt í ritmáli
að skeyta "v" fyrir framan merkingartengd útgáfunúmer til að gefa til kynna að 
um útgáfunúmer sé að ræða. Þá er "v" skammstöfun á "version" og sést oft í 
samstæðustjórnunarkerfum. Dæmi: 'git tag v1.2.3 -m "Útgáfa númer 1.2.3"', en þá 
er "v1.2.3" nafn á merki og merkingartengda útgáfunúmerið "1.2.3".


Um
---

Skilgreining merkingartengdra útgáfunúmera er samin af [Tom
Preston-Werner](http://tom.preston-werner.com), höfundi Gravatar og 
meðstofnandi GitHub.

Ef þú vilt gefa endurgjöf, vinsamlegast [opna mál á GitHub]
(https://github.com/mojombo/semver/issues).


Leyfi
-----

Creative Commons - CC BY 3.0
http://creativecommons.org/licenses/by/3.0/
