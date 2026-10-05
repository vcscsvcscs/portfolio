+++
draft = false
date = 2026-10-04T22:00:00+02:00
title = "HackYeah 2026: Pomóc ja Smart City -haaste"
summary = "Vietin Apexlabin tiimimme kanssa 24 tuntia HackYeahissa TAURON Arena Krakówissa ja rakensimme Pomócin: kansalaisille tarkoitetun läheisyysverkon, jolla naapurit jakavat tavaroita tavallisena päivänä ja hätäviestit kulkevat, kun mobiiliverkko pimenee."
tags = ["hackathon", "smart-city", "civic-tech", "mesh", "ai", "krakow","poc","simulation","dual-use"]
categories = ["hackathons"]
+++

## HackYeah 2026
**3.–4. lokakuuta 2026**  
**TAURON Arena Kraków**  
24 tunnin lähitapahtuma · Euroopan suurin paikan päällä järjestettävä hackathon · 3000 osallistujaa · 1–6 hengen tiimit · jokainen osallistuja vähintään 18-vuotias

Vietin viikonlopun **HackYeah 2026** -tapahtumassa **Fábi Tamásin** ja **Magyar Dánielin** kanssa. Kilpailimme nimellä **Apexlab** avoimessa **Smart City** -tehtävässä.

![Apexlab-tiimi HackYeah 2026 -tapahtumassa](/images/hackyeah-2026-team.jpg)

HackYeah on 24 tunnin hackathon: tiimit saavat oikean toimeksiannon, rakentavat toimivan prototyypin ja istuvat samassa tilassa mentoreiden, kumppanien ja muun yhteisön kanssa. Koodaus alkoi lauantaina kello 11.00. Tila on konserttiareena, ja mittakaavan huomaa ensimmäisenä: lattia, valotrussit ja se, kuinka monta tiimiä rakentaa samassa hallissa.

## Haaste

Kaupungit toimivat jo infrastruktuurinsa äärirajoilla. Väestö kasvaa, ja liikkumisen, energian, liikenteen ja tiedonsaannin pitää toimia nopeammin ja luotettavammin kuin ennen.

Smart City -tehtävässä haettiin työkalua, sovellusta tai prototyyppiä, joka auttaa kaupunkia toimimaan paremmin arjessa. Liikkuminen, resurssien hallinta, viestintä asukkaiden kanssa, kriisitoiminta, kaupunkidata, julkiset palvelut, elämänlaatu: mikä tahansa näistä kävi, kunhan tulos vastasi oikeaan ongelmaan. Suunta oli selvä: rakenna teknologiaa, joka helpottaa tavallista kaupunkielämää. Sarjan palkintopotti oli **5 000 PLN**.

## Pomóc

Vastauksemme oli **Pomóc**, kansalaisille tarkoitettu läheisyysverkko, joka pyörii laitteilla, joita kaupungissa jo on.

Vika näyttää kahdelta eri vialta. Tavallisena tiistaina porakonetta käytetään sen koko elinaikana noin 13 minuuttia, ja defibrillaattori voi roikkua seinällä noin 80 metrin päässä sydänpysähdyksestä. Huonona päivänä mobiiliverkko katkeaa usein ensimmäisenä, eikä lähellä jo olevaa apua tavoiteta. Molemmat ovat reititysongelmia samassa graafissa: kuka on fyysisesti kenen lähellä.

Pomócissa on yksi protokolla, yksi identiteetti ja kaksi sääntöjoukkoa.

**Rauhan aikana** se on naapuruston jakamisverkko. Lainaa porakone, kysy, kenellä on ylimääräinen turvaistuin, luovuta parkkipaikka. Kantama on rajattu hyppyihin, joten pyyntö pysyy lähialueella suunnitellusti. Jakaminen on oletuksena ilmaista. Lainanantaja voi pyytää pientä maksua, lainaaja näkee sen ennen hyväksymistä, ja he sopivat maksun keskenään. Pomóc vain näyttää maksun.

**Hätätilassa** samat identiteetit ja samat laitteet kuljettavat allekirjoitettuja viestejä sen jälkeen, kun operaattoriverkko on kaatunut. Kotireitittimet muodostavat Wi-Fi-meshin. Puhelimet välittävät Bluetooth LE:llä. Viralliset hälytykset, ”olen kunnossa” -kuittaukset ja henkeä pelastavat pyynnöt, kuten defibrillaattori, EpiPen tai tulipalo, etenevät hyppy hypyltä. Store-and-forwardilla kahden saarekkeen välillä kävelevä ihminen kantaa viestin aukon yli.

Hätätilassa on kolme tasoa, koska tukiasemakatkos ja aseellinen hyökkäys vaativat eri sääntöjä.

| | L1 Häiriö | L2 Katastrofi | L3 Turvallisuus |
|---|---|---|---|
| Tyypillinen syy | Tukiasemakatkos, kaapelikatko, kyberhyökkäys | Tulva, myrsky, pitkä sähkökatko | Aseellinen hyökkäys, hybridiuhka |
| Kuka voi käynnistää sen | Paikallinen automaatio tai allekirjoitettu julistus | Paikallisviranomaisen allekirjoitettu julistus | Paikallisviranomaisen allekirjoitettu julistus |
| Mitä asukkaat voivat lähettää | Henkeä pelastava, turvallisuus, kuittaus, paikallinen tieto | Sama, sekä jäsennellyt pyynnöt reitittimen portaalin kautta | Henkeä pelastava, turvallisuus, kuittaus. Paikallinen tieto on pois käytöstä |

Tukiasemia häiritsemällä järjestelmän voi pakottaa enintään L1:een. L2 ja L3 vaativat allekirjoituksen. L3:ssa puhelimet lakkaavat levittämästä naapurilistojaan, joten mesh pysyy keinona pyytää apua eikä muutu eläväksi kartaksi siitä, missä ihmiset ovat.

Kyse on tavallisesta julkisen avaimen infrastruktuurista, jonka juurivarmenne on kansalaispohjainen. Puhelin luo avaimensa suojatussa sirussa, ja yksityinen avain pysyy siellä. Henkilö todistaa henkilöllisyytensä kansallisella identiteettilompakolla: Puolassa mObywatel, muualla EUDI-lompakko. Viranomainen allekirjoittaa lyhytikäisen kansalaisvarmenteen. Mikä tahansa solmu voi tarkistaa viestin ilman verkkoa, koska viranomaisen juuriavain on jo sovelluksessa. Reitittimillä on vain välitysvarmenteet. Ne välittävät liikennettä, ja välitysvarmenteella allekirjoitettu pyyntö hylätään. Rajoitus on kryptografinen.

![Miten Pomóc rakentuu: viranomainen, operaattoreiden reitittimet runkona ja puhelimet reunalla](/images/hackyeah-2026-architecture.png)

Pomóc kokonaisena kaupunkijärjestelmänä on visio. 24 tunnissa rakensimme sille perusteen: vuorovaikutteisen simulaation protokollasta todellisella palalla kaupunkia.

## Mitä voi kokeilla

Demo on selainsimulaatio Krakówista Veikselin mutkassa: Kazimierz, Stradom, Stare Podgórze, Dębniki, Grzegórzki ja Zabłocie. Siemen 42 lataa aina saman kartan, joten harjoiteltu ajo toistuu täsmälleen samanlaisena. Puhelimet kävelevät, pyöräilevät ja ajavat katugraafilla. Reitittimet seisovat katujen välisissä kortteleissa. Joki ja puistot pysyvät tyhjinä.

Paneelista voi pudottaa mobiiliverkon, katkaista sähköverkon, julistaa L1:n, L2:n tai L3:n, lähettää virallisen hälytyksen, lähettää asukkaan pyynnön, hyväksyä sellaisen ja syöttää väärennetyn pyynnön, jonka jokainen naapuri hylkää. Paketit liikkuvat yhden hypyn tickiä kohden, joten tulviminen, hyppyrajat, kaksoiskappaleet, vanheneminen ja store-and-forward näkyvät kartalla. Mittaristo laskee, kuka on yhä tavoitettavissa, toimitukset viestiluokittain ja sen, miksi paketti hylättiin.

![Pomóc-simulaatio L1-sähkökatkon aikana Kazimierzissa](/images/hackyeah-2026-sim.png)

Live-demo on osoitteessa [pomoc.varghacsongor.hu](https://pomoc.varghacsongor.hu/). Samasta ajosta on video myös [YouTubessa](https://youtu.be/VvQO707MbZQ).

Säännöt ovat puhtaassa TypeScript-moottorissa. React ja Mantine piirtävät kartan ja ohjaimet. Simulaatiossa kryptografia on luottamusmerkki allekirjoittajalla, ja protokollan ajastimet on tiivistetty niin, että sähkökatko ja tilan vaihto näkyvät minuutissa. Demo näyttää, miten mesh käyttäytyy: kuka kuulee vielä kenet, kun tukiasemat kaatuvat ja akuttomat reitittimet pimenevät.

## Sama suunnitelma, kaksi malliparia

Rakentamisen ohessa ajoimme pienen vertailun.

Kirjoitimme toteutussuunnitelman **Claude Fable 5.1**:llä Ultramodessa ja veimme saman suunnitelman läpi kahdesti. Toinen ajo käytti **Fable 5.1**:tä ja **Opus**-agentteja. Toinen käytti **Sonnet 5.5**:tä ja **Haiku**-agentteja.

Kiinnostavaa oli, kuinka paljon laadusta oli jo suunnitelmassa. Molemmat ajot päättyivät toimivaan tuotteeseen. Fable- ja Opus-versio oli hiottumpi ja ominaisuuksiltaan rikkaampi. Sonnet- ja Haiku-versio näytti silti ehjältä ja teki työnsä. Ero niiden välillä oli pienempi kuin odotin. Edullisempana parina Sonnet ja Haiku kestivät vertailun, koska ne toteuttivat suunnitelmaa, jonka Fable oli jo tehnyt hyvin konkreettiseksi. Vahvempi pari sai samat ohjeet ja nosti tuloksen vankasta poikkeukselliseksi.

## Areena ja Kraków

![HackYeah-lattia TAURON Arena Krakówissa](/images/hackyeah-2026-arena.jpg)

Tämä oli ensimmäinen hackathonini tällaisessa paikassa. Halli, valo ja tiimien tiheys tekivät 24 tunnista festivaalin, joka sattui olemaan ohjelmistoista.

![HackYeah areenan valoissa](/images/hackyeah-2026-arena-lights.jpg)

Puolan IT-ala jätti vahvan vaikutelman. Ala on pitkällä ja elinvoimainen. Ehdin puhua ihmisten kanssa oman pöytämme ulkopuolellakin, ja ne keskustelut olivat oikeasti osa viikonloppua.

![TAURON Arena Krakówin ulkopuolella](/images/hackyeah-2026-tauron-arena.jpg)

Kraków oli tapahtuman veroinen. Se on kaunis kaupunki, ja ruoka oli erinomaista.

Yksi yksityiskohta hallista jää mieleen. Järjestäjät jakoivat energiashotin, Strzał Energii: **200 mg kofeiinia 120 ml:ssa**. Se on paljon kofeiinia hyvin pienessä pullossa.

![Hackathonin 120 ml:n energiashot](/images/hackyeah-2026-energy-shot.jpg)

Emme päässeet finaaliin. Olen silti ylpeä tiimistä ja siitä, mitä teimme. Tom ja Dani olivat mainioita tiimikavereita. Työskentelimme idean parissa todella intohimoisesti, pidimme suunnitelmaa paineessa, kunnes se kesti, ja käteen jäi demo, jonka näytän mielelläni.

En unohda, millaista oli olla paikalla Euroopan suurimmassa paikan päällä järjestettävässä hackathonissa.

[Kokeile simulaatiota](https://pomoc.varghacsongor.hu/) · [Katso video](https://youtu.be/VvQO707MbZQ)
