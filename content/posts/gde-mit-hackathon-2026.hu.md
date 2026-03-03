+++
draft = false
date = 2026-02-28T00:00:00+01:00
title = "GDE MIT Hackathon 2026: Eva, egy voice-first egészségasszisztens"
summary = "Részt vettem a budapesti GDE MIT Hackathonon, ahol megépítettem az Evát: egy voice-first egészség-naplót, ami összegyűjti a health adatokat és orvosoknak megosztható riportokat készít — Azure Cognitive Services, OpenAI modellek, Go, Docker Compose és Flutter segítségével."
tags = ["hackathon", "healthcare", "azure", "ai", "speech", "go", "flutter", "docker"]
categories = ["hackathons"]
+++

## GDE MIT Hackathon 2026
**2026. február 27–28.**  
**Gábor Dénes Egyetem, Budapest (Fejér Lipót u. 70, 1119)**  
~30 órás offline innovációs maraton • ~100 résztvevő • oktatás + egészségügyi kihívások

A **GDE MIT Hackathon** egy intenzív, offline innovációs hétvége volt, ahol tapasztalt fejlesztők és lelkes kezdők vegyes csapatokban dolgoztak valós problémákon **oktatás** és **egészségügy** témában. Két nap alatt az ötleteléstől a kódoláson át a pitch-ig jutottunk, a végén pedig szakmai zsűri értékelte a megoldásokat.

Én ezen a hackathonon **szólóban** indultam az **egészségügyi kihívásban**.

## Amit építettem: Eva, Health Assistant
Megépítettem az **Evát**, egy voice-first egészség-naplót, aminek a célja, hogy könnyebb legyen a mindennapi egészségadatokat rögzíteni, átlátni — és főleg: **érthetően megosztani az orvossal**.

**Alapötlet:**
- A felhasználó hanggal (és strukturált inputokkal) naplóz, az app pedig **megosztható, orvosbarát riportokat** generál.

**Az Eva által összegyűjtött/aggregált adatok iránya:**
- Tünetek
- Életjelek (vitals)
- Gyógyszerek
- Fitness / aktivitás
- Menstruációs ciklus

## Tech stack
Próbáltam gyorsan haladni, de közben reális architektúrát tartani:
- **Azure**: Cognitive Services (speech) + AI Foundry OpenAI modellekhez
- **Backend**: **Go** + **Docker Compose**
- **Mobil**: **Flutter**
- **Munkafolyamat**: Spec-alapú fejlesztés **Kiro IDE**-ben, és **Cursor (Opus 4.6)** a nehezebb problémák gyors megoldásához

## Ami nem úgy alakult, ahogy terveztem
Végül **nem adtam le** a munkámat — ami nálam első. Rosszul lettem, és a második nap reggelén haza kellett mennem, még azelőtt, hogy rendesen össze tudtam volna rakni a demót és a beadást.

Frusztráló volt, de arra is emlékeztetett, hogy a hackathon nem csak mérnöki munka: sokszor a terhelhetőség és az egészség is döntő. Ettől függetlenül büszke vagyok az Eva irányára, és szeretném továbbvinni az ötletet.

## Közösség és köszönet
Az egyik legjobb része az volt, hogy sok **nemzetközi hallgatóval** találkoztam, és lett pár új ismerősöm/barátom (Krigis is).

Köszönet a **Gábor Dénes Egyetemnek**, hogy bevállalt és megszervezett egy ilyen jellegű eseményt. Remélem, más egyetemeket is inspirál majd Magyarországon, hogy több hasonló hackathont hozzanak létre — mert ezek tényleg lendületet adnak, és összehozzák az embereket.
