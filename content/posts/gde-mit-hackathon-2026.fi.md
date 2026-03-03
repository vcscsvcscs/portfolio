+++
draft = false
date = 2026-02-28T00:00:00+01:00
title = "GDE MIT Hackathon 2026: Eva, ääni ensin -terveysavustaja"
summary = "Osallistuin Budapestissa järjestettyyn GDE MIT Hackathoniin ja rakensin Evan: ääni ensin -terveyspäiväkirjan, joka yhdistää terveysdataa ja tuottaa jaettavia raportteja lääkäreille — Azure Cognitive Servicesin, OpenAI-mallien, Gon, Docker Composen ja Flutterin avulla."
tags = ["hackathon", "healthcare", "azure", "ai", "speech", "go", "flutter", "docker"]
categories = ["hackathons"]
+++

## GDE MIT Hackathon 2026
**27.–28. helmikuuta 2026**  
**Gábor Dénes -yliopisto, Budapest (Fejér Lipót u. 70, 1119)**  
~30 tunnin offline-innovaatiomaraton • ~100 osallistujaa • koulutus + terveydenhuollon haasteet

**GDE MIT Hackathon** oli noin 30 tunnin offline-innovaatiomaraton Gábor Dénes -yliopistolla, joka kokosi yhteen kokeneita kehittäjiä ja kunnianhimoisia uusia tekijöitä ratkomaan oikean maailman ongelmia **koulutuksessa** ja **terveydenhuollossa**. Kahden päivän aikana ideoitiin, koodattiin ja pitchattiin ammattiraadille, ja parhaat ratkaisut palkittiin.

Osallistuin mukaan ja päätin kilpailla **yksin** **terveydenhuollon haasteessa**.

## Mitä rakensin: Eva, Health Assistant
Rakensin **Evan**, ääni ensin -terveyspäiväkirjan, jonka tavoitteena on helpottaa arjen terveysdatan tallentamista, trendien ymmärtämistä ja ennen kaikkea tärkeiden tietojen **selkeää jakamista lääkärille**.

**Ydinajatus:**
- Kirjaa terveysdataa luontevasti puheella (ja strukturoituina syötteinä) ja muunna se **jaettaviksi, lääkärikäyttöön sopiviksi raporteiksi**.

**Data, jota Eva pyrkii yhdistämään:**
- Oireet
- Vitaalit / elintoiminnot
- Lääkitys
- Kuntoilu/aktiivisuus
- Kuukautiskierto

## Tekninen toteutus
Tavoitteena oli edetä nopeasti, mutta pitää arkkitehtuuri realistisena:
- **Azure**: Cognitive Services (Speech) + AI Foundry OpenAI-malleille
- **Backend**: **Go** + **Docker Compose**
- **Mobiili**: **Flutter**
- **Työtapa**: Speksipohjainen kehitys **Kiro IDE**:llä, ja **Cursor (Opus 4.6)** vaikeampien ongelmien ratkaisuun

## Mikä ei mennyt suunnitelmien mukaan
Lopulta **en saanut palautettua** työtäni — ensimmäistä kertaa. Tulin kipeäksi ja jouduin lähtemään toisen päivän aamuna, ennen kuin ehdin viimeistellä demon ja varsinaisen palautuksen.

Se harmitti, mutta muistutti myös siitä, että hackathonit eivät ole pelkkää ohjelmointia: jaksaminen ja terveys ratkaisevat paljon. Silti olen ylpeä siitä, mihin suuntaan Eva ehti kehittyä lyhyessä ajassa, ja haluan jatkaa idean kehittämistä.

## Yhteisö ja kiitokset
Yksi parhaista puolista oli tutustua moniin **kansainvälisiin opiskelijoihin**, ja sain myös uusia ystäviä (Krigis mukaan lukien).

Suuret kiitokset **Gábor Dénes -yliopistolle** tällaisen hackathonin järjestämisestä. Toivon, että se inspiroi muitakin yliopistoja Unkarissa panostamaan vastaaviin tapahtumiin — ne rakentavat yhteisöä, luovat momentumia ja yhdistävät ihmisiä.
