+++
draft = false
date = 2026-05-01T00:00:00+02:00
title = "Ender 3-tól az Anycubic Kobra X-ig: amikor a 3D nyomtatás végre magától működik"
summary = "Személyes visszatekintés a 3D nyomtatási utamra: Ender 3 tuning, saját alkatrészek, Marlin firmware, majd az Anycubic Kobra X sebessége, megbízhatósága és automatizáltsága."
tags = ["3d-printing", "maker", "hardware", "ender3", "anycubic", "diy"]
categories = ["projects"]
+++

## Egy hosszú maker út kezdete
Nagyjából **2018-2019** körül kezdtem el 3D nyomtatással foglalkozni, amikor megvettem az első nyomtatómat, egy **Ender 3-at**. Akkoriban a hobbi 3D nyomtatás még sok türelmet igényelt. A gép olcsó és sokoldalú volt, de a folyamatosan jó eredményhez meg kellett tanulni a nyomtatót, a szeletelőt, az anyagokat és azokat az apró mechanikai részleteket, amelyeken egy nyomat sikere múlhat.

Az első nagyobb projektem szinte azonnal megérkezett. Volt egy egyedileg készített tetőcsomagtartó táskatartónk egy **VW Caddyhez**, amelyhez saját adaptereket és rögzítőelemeket terveztem és nyomtattam. Ez a projekt nagyon gyorsan megmutatta a 3D nyomtatás valódi értékét: nem kellett arra várni, hogy létezzen megfelelő alkatrész a piacon, hanem pontosan azt lehetett megtervezni, tesztelni és legyártani, amire szükség volt.

Később sok kisebb kütyüt, praktikus alkatrészt és kísérleti tárgyat nyomtattam, főleg **PLA** anyagból. A minőség eleinte nem volt mindig kiemelkedő, de minden nyomat tanított valamit. Sokat kísérleteztem szeletelő beállításokkal, kalibrációval, apró géptuninggal és azzal, hogy hol vannak a nyomtató valódi határai.

## Egy sokat módosított Ender 3
Az évek alatt az Ender 3 több átalakításon is átesett. Kipróbáltam a **direct drive extruder** átalakítást, majd később visszatértem a **Bowden csöves** megoldáshoz. Került rá **üveg tárgyasztal**, sok mechanikai finomhangolás, és lépésről lépésre egyre használhatóbb géppé vált.

Tavaly véletlenül megsütöttem az eredeti alaplapot, ezért egy modernebb lapra kellett cserélnem, amelyre lefordítottam a legfrissebb **Marlin** firmware-t. A javításból végül egy nagyobb fejlesztési kör lett: került rá automatikus tárgyasztal-szintezés, szíjhajtású dupla Z tengely, DIY IKEA asztalos burkolat és **PEI nyomtatófelület** is.

Ezekkel a fejlesztésekkel az Ender 3 sokkal kiszámíthatóbb és jobb minőségű gép lett. Körülbelül **60 mm/s** sebességen már stabil, jó minőségű nyomatokat tudott készíteni. Ennek ellenére továbbra is olyan nyomtató maradt, amely figyelmet igényelt. A sikeres nyomatokhoz sokszor ellenőrzés, állítgatás, finomhangolás és néha egyszerűen türelem kellett.

## Ugrás a Kobra X-re
Januárban megjelent az **Anycubic Kobra X**, nagyjából **280 EUR** áron, és az ár-érték aránya azonnal feltűnt. Gyárilag olyan funkciókat kínált, amelyek néhány éve még inkább felső kategóriás extráknak számítottak:

- Négy filament egyidejű támogatása
- Wi-Fi és teljes távoli vezérlés
- Pontos automatikus tárgyasztal-szintezés
- Kamerás spaghetti detection
- Gyorsuláskompenzáció
- Smart flow control
- Hot-swap hotend
- 260 x 260 mm-es tárgyasztal
- 0,02 mm-es megadott pontosság
- 300-600 mm/s nyomtatási sebesség

Ezért az árért ez rendkívül erős csomag. Több évnyi budget nyomtatós kompromisszum után számomra ez az egyik legjobb ár-érték arányú gépnek tűnt, amit valaha láttam, ezért megrendeltem. A várólista hosszú volt, így a rendeléstől a kiszállításig nagyjából **három és fél hónap** telt el.

## Tinkering helyett nyomtatás
Amikor végre megérkezett a nyomtató, a különbség azonnal érezhető volt. Összeszerelés és teljesen automatikus kalibráció után már gyárilag kiváló minőségben nyomtatott. Az Ender 3-hoz képest nemcsak gyorsabb volt, hanem sokkal kevesebb figyelmet is igényelt.

A sebesség teljesen megváltoztatta, hogyan állok a projektekhez. A Kobra X-en már a harmadik nyomatom egy **20 órás állólámpa** volt. Ugyanez az Ender 3-on kockázatos, körülbelül 80 órás nyomtatás lett volna, jóval nagyobb hibalehetőséggel. A Kobra X első próbálkozásra tökéletesen kinyomtatta.

Három hét alatt szinte folyamatosan nyomtattam vele, és több tárgy készült el, mint korábban az erősen módosított Ender 3-mal összesen. Ennek egyszerű oka van: nem kell folyamatosan szerelni és állítgatni. A tapadás erős, a kalibráció megbízható, és a nyomtató inkább eszköznek érződik, nem pedig külön projektnek.

## Mi következik
A következő lépés egy rendes enclosure építése lesz. Elég sokat nyomtatok **ASA** és **ABS** anyagokkal, és bár a modern draft shield opciók kisebb alkatrészeknél sokat segítenek, a vetemedés még mindig probléma. Volt olyan nyomat, ahol a tárgyasztal tapadása annyira erős volt, hogy az alkatrész nem vált le, hanem a belső feszültség miatt az egész nyomtatott forma meghajlott.

A legizgalmasabb számomra nem csak maga az új nyomtató, hanem az a fejlődés, amit képvisel. Néhány év alatt a hobbi 3D nyomtatás eljutott onnan, hogy a folyamatos tuning szinte alapelvárás volt, oda, hogy egy budget gép automatizálást, távoli vezérlést, többanyag-támogatást, fejlett kalibrációt és nagyon nagy sebességet kínál.

Számomra a Kobra X jó emlékeztető arra, miért szerettem bele eredetileg a 3D nyomtatásba: mert gyorsan lehet ötletekből fizikai tárgyakat készíteni. A különbség az, hogy ma már a technológia sokkal gyakrabban eltűnik az útból, és ettől az alkotási folyamat sokkal élvezetesebb.
