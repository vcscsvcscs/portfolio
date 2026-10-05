+++
draft = false
date = 2026-10-04T22:00:00+02:00
title = "HackYeah 2026: Pomóc és a Smart City kihívás"
summary = "Az Apexlab csapatával 24 órát töltöttem a krakkói HackYeah-n, a TAURON Arénában. A Pomóc városi hálózat a közelben lévő eszközökön fut: hétköznap a szomszédok megosztják egymással, amijük van, ha pedig elmegy a mobilhálózat, ugyanaz a rendszer viszi a segélyüzeneteket."
tags = ["hackathon", "smart-city", "civic-tech", "mesh", "ai", "krakow","poc","simulation","dual-use"]
categories = ["hackathons"]
+++

## HackYeah 2026
**2026. október 3–4.**  
**TAURON Arena Kraków**  
24 órás helyszíni hackathon · Európa legnagyobb helyszíni hackathonja · 3000 résztvevő

A hétvégét a **HackYeah 2026**-on töltöttem **Fábi Tamással** és **Magyar Dániellel**. **Apexlab** néven indultunk a **Smart City** nyílt feladatán.

![Az Apexlab csapata a HackYeah 2026-on](/images/hackyeah-2026-team.jpg)

A HackYeah 24 órás hackathon: a csapatok valódi feladatot kapnak, működő prototípust építenek, és mentorokkal, partnerekkel és a közösség többi tagjával egy teremben dolgoznak. A kódolás szombaton 11:00-kor indult. A terem egy koncertaréna, és először a lépték tűnik fel: a padló, a világítás, és hogy hány csapat épít ugyanabban a csarnokban.

## A kihívás

A városok infrastruktúrája már most a teljesítőképessége határán van. A népesség nő, a közlekedésnek, az energiának, a szállításnak és az információhoz jutásnak pedig gyorsabbnak és megbízhatóbbnak kell lenniük, mint korábban.

A Smart City feladat olyan eszközt, alkalmazást vagy prototípust kért, amely a hétköznapokban segíti a város működését. Mobilitás, erőforrás-gazdálkodás, kommunikáció a lakókkal, válságkezelés, városi adatok, közszolgáltatások, életminőség: bármelyik megfelelő volt, ha a megoldás valós problémára válaszolt. Az irány egyértelmű volt. Olyan technológiát kellett építeni, amely megkönnyíti a városi hétköznapokat. A kategória díjalapja **5 000 PLN** volt.

## Pomóc

A válaszunk a **Pomóc** lett: egy polgári hálózat, amely a városban már meglévő, egymáshoz közeli eszközökön fut.

A helyzet elsőre két külön hibának látszik. Egy átlagos kedd képe ez: egy fúró a teljes élettartama alatt nagyjából 13 percet dolgozik, egy defibrillátor pedig egy falon lóghat mintegy 80 méterre egy szívleállástól. Rossz napon a mobilhálózat gyakran esik ki elsőként, és a közelben lévő segítség nem érhető el. Mindkettő útválasztási probléma ugyanazon a gráfon: kihez ki van fizikailag közel.

A Pomóc egy protokollból, egy személyazonosságból és két szabályrendszerből áll.

**Békeidőben** a szomszédok ezen a hálózaton osztják meg egymással, amijük van. Kölcsönkérsz egy fúrót, megkérdezed, kinél van tartalék gyerekülés, átadsz egy parkolóhelyet. Az üzenet csak korlátozott számú ugrásig jut el, ezért a kérés a protokoll miatt a környéken marad. A megosztás alapból ingyenes. A kölcsönadó kérhet egy kis díjat, a kölcsönkérő ezt elfogadás előtt látja, és ketten közvetlenül rendezik. A Pomóc csak a díjat mutatja.

**Vészhelyzetben** ugyanazok a személyazonosságok és ugyanazok az eszközök viszik az aláírt üzeneteket, miután a szolgáltatói hálózat eltűnt. Az otthoni routerek Wi-Fi mesh-t alkotnak. A telefonok Bluetooth LE-n továbbítanak. A hivatalos riasztások, a „jól vagyok” jelentkezések és az életmentő kérések, például egy defibrillátor, egy EpiPen vagy egy tűz, ugrásról ugrásra mennek tovább. Store-and-forward esetén, aki két sziget között gyalogol, átviszi az üzenetet a résen.

A vészhelyzeti módnak három szintje van, mert egy cella kiesését és egy fegyveres támadást nem lehet ugyanazokkal a szabályokkal kezelni.

| | L1 Zavar | L2 Katasztrófa | L3 Biztonság |
|---|---|---|---|
| Tipikus ok | Cella kiesése, kábel elvágása, kibertámadás | Árvíz, vihar, hosszú áramszünet | Fegyveres támadás, hibrid fenyegetés |
| Ki aktiválhatja | Helyi automatika vagy aláírt kihirdetés | A helyi hatóság aláírt kihirdetése | A helyi hatóság aláírt kihirdetése |
| Mit küldhetnek a lakók | Életmentő, biztonsági, jelentkezés, helyi információ | Ugyanez, plusz strukturált kérések a router portálján | Életmentő, biztonsági, jelentkezés. A helyi információ ki van kapcsolva |

A cellák zavarásával legfeljebb az L1 kényszeríthető ki. Az L2 és az L3 aláírást igényel. L3 esetén a telefonok nem adják tovább a szomszédlistájukat, így a mesh csak segítségkérésre szolgál, és nem lesz belőle élő térkép arról, hol vannak az emberek.

A bizalom szabványos nyilvános kulcsú infrastruktúrán alapul, polgári gyökértanúsítvánnyal. A telefon a kulcsát a biztonsági chipben generálja, a privát kulcs ott marad. A felhasználó egy nemzeti identitástárcán keresztül igazolja magát: Lengyelországban a mObywatel, máshol egy EUDI-tárca. A hatóság rövid életű polgári tanúsítványt ír alá. Bármely csomópont offline ellenőrizheti az üzenetet, mert a hatóság gyökérkulcsa már az alkalmazásban van. A routerek csak relay tanúsítványt kapnak. Továbbítják a forgalmat, és a relay tanúsítvánnyal aláírt kérés eldobódik. Ez kriptográfiai korlát.

![Hogyan áll össze a Pomóc: a hatóság, az internetszolgáltatók routerei gerincként, és a telefonok a hálózat szélén](/images/hackyeah-2026-architecture.png)

A Pomóc teljes városi rendszerként még csak vízió. 24 óra alatt azt építettük meg, ami ezt megmutatja: a protokoll interaktív szimulációját a város egy valós részén.

## Amit ki lehet próbálni

A demó a Visztula kanyarulatának böngészős szimulációja: Kazimierz, Stradom, Stare Podgórze, Dębniki, Grzegórzki és Zabłocie. A 42-es seed mindig ezt a térképet tölti be, ezért egy begyakorolt menet pontosan újrajátszható. A telefonok gyalogolnak, kerékpároznak és autóznak az utcák gráfján. A routerek a tömbökben állnak. A folyó és a parkok üresen maradnak.

A panelről le lehet kapcsolni a mobilhálózatot, le lehet vágni az áramot, ki lehet hirdetni az L1-et, az L2-t vagy az L3-at, hivatalos riasztást lehet küldeni, lakossági kérést lehet indítani, el lehet fogadni egyet, és be lehet juttatni egy hamis kérést, amelyet minden szomszéd eldob. A csomagok minden tickben egy ugrást tesznek, ezért az elárasztás, az ugrások korlátja, a duplikátumok, a lejárat és a store-and-forward mind látszik a térképen. Egy összesítő mutatja, ki érhető még el, a kézbesítést típusonként, és hogy egy csomag miért esett ki.

![A Pomóc szimulációja egy L1-es áramkimaradás alatt Kazimierzben](/images/hackyeah-2026-sim.png)

Az élő demó a [pomoc.varghacsongor.hu](https://pomoc.varghacsongor.hu/) címen fut. Ugyanennek a menetnek a végigvezetése [YouTube-on](https://youtu.be/VvQO707MbZQ) is megvan.

A szabályok egy tiszta TypeScript motorban futnak. A térképet és a vezérlőket a React és a Mantine rajzolja. A szimulációban a kriptográfia csak egy, az aláíróhoz tartozó bizalmi jelző, a protokoll időzítői pedig össze vannak nyomva, hogy egy áramszünet és egy módváltás egy percen belül megjelenjen. A demó a mesh viselkedéséről szól: ki hall még kit, amikor a cellák leállnak, és elsötétülnek azok a routerek, amelyekben nincs tartalék akku.

## Ugyanaz a terv, két páros

Az építéssel párhuzamosan egy kis összehasonlítást is futtattunk.

A végrehajtási tervet **Claude Fable 5.1**-gyel írtuk Ultramode-ban, majd ugyanezt a tervet kétszer vittük végig. Az egyik futásban **Fable 5.1** dolgozott **Opus** ügynökökkel. A másikban **Sonnet 5.5** dolgozott **Haiku** ügynökökkel.

Az volt az érdekes, hogy a minőségből mennyi volt már meg a tervben. Mindkét futásból működő termék lett. A Fable és az Opus változata lett a kifinomultabb, és több funkcióval jött ki. A Sonnet és a Haiku változata így is rendben volt, és elvégezte a dolgát. A kettő közötti különbség kisebb volt, mint vártam. Költségkímélő párosként a Sonnet és a Haiku megállták a helyüket, mert olyan tervet hajtottak végre, amelyet a Fable már nagyon konkréttá tett. Az erősebb páros ugyanazokat az utasításokat kapta, és az erős eredményt kivételessé vitte.

## Az aréna és Krakkó

![A HackYeah terme a krakkói TAURON Arénában](/images/hackyeah-2026-arena.jpg)

Ez volt az első hackathonom ilyen helyszínen. A csarnok, a fény és a csapatok sűrűsége miatt a 24 óra fesztiválnak érződött, csak éppen a szoftverről szólt.

![A HackYeah az aréna fényeiben](/images/hackyeah-2026-arena-lights.jpg)

A lengyel IT-szektor erős benyomást hagyott. Fejlett és élénk. Volt időm a saját asztalunkon kívül is beszélgetni, és ezek a beszélgetések tényleg hozzátartoztak a hétvégéhez.

![A krakkói TAURON Aréna előtt](/images/hackyeah-2026-tauron-arena.jpg)

Krakkó illett az eseményhez. Gyönyörű város, és az étel kiváló volt.

Egy részlet a helyszínről velem marad. A szervezők energiaital-shotot osztottak, Strzał Energii: **200 mg koffein 120 ml-ben**. Ez sok koffein egy nagyon kis üvegben.

![A hackathon 120 ml-es energiaital-shotja](/images/hackyeah-2026-energy-shot.jpg)

Nem jutottunk a döntőbe. A csapatra és arra, amit csináltunk, így is büszke vagyok. Tom és Dani remek csapattársak voltak. Szenvedéllyel dolgoztunk az ötleten, addig alakítottuk a tervet, amíg összeállt, és olyan demóval jöttünk el, amelyet szívesen mutatok.

Hogy ott lehettem Európa legnagyobb helyszíni hackathonján, olyan élmény, amelyet nem felejtek el.

[Próbáld ki a szimulációt](https://pomoc.varghacsongor.hu/) · [Nézd meg a videót](https://youtu.be/VvQO707MbZQ)
