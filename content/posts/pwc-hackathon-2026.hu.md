+++
draft = false
date = 2026-04-16T00:00:00+02:00
title = "PwC Hackathon 2026: Org Pondus és AI-alapú szervezetfejlesztés"
summary = "Csapatommal részt vettünk a PwC Hackathon 2026-on, ahol az Org Pondus koncepciót mutattuk be: egy AI-ügynökökre és súlyozott gráfra épülő megoldást adatvezérelt hiring, workforce planning, megtartás és szervezeti stratégia támogatására."
tags = ["hackathon", "pwc", "ai", "agents", "aws", "bedrock", "agentcore", "knowledge-graph", "hr-tech"]
categories = ["hackathons"]
+++

## PwC Hackathon 2026
**2026. április 16.**  
**PwC Magyarország, Budapest**  
Előszűrés • üzleti koncepció pitch • MVP canvas • ROI-tervezés • hackathon megvalósítási terv

Csapatommal részt vettünk a **PwC Hackathon 2026-on**, egy kiemelt és a megszokottól eltérő felépítésű budapesti hackathonon. A csapatunkban **Erdős Péter Zsombor**, **Vargha Bendegúz Attila** - a testvérem - és én dolgoztunk együtt, **The Professionals** néven.

Ez az esemény több szempontból is más volt, mint a legtöbb hackathon. A döntő építési szakasz előtt először egy előszűrésen kellett átjutni, majd egy komoly üzleti pitch anyagot kellett elkészíteni: **6-8 diás üzleti koncepciót**, **MVP canvas-t**, **ROI modellt** és egy reális **hackathon munkatervet**. Végül nem kerültünk be a továbbjutó 15 csapat közé, de az élményt így is nagyon értékesnek tartom. Egy tartalmas koncepciót dolgoztunk ki, nyomás alatt finomítottuk, és közben kiváló szakmai kapcsolatokat is szereztünk.

![The Professionals csapat a PwC Hackathon 2026-on](/images/pwc-hackathon-2026-team.png)

Számomra az egyik legnagyobb érték az volt, hogy lehetőségem volt beszélni a PwC Magyarország vezetésével, valamint technikai beszélgetéseket folytatni a Cloud Engineering és az AI Engineering vezetőivel. Ezek a beszélgetések sokkal többé tették az eseményt egy versenynél: ritka lehetőség volt egy ötletet olyan szakemberekkel validálni, akik egyszerre értik az enterprise technológiát és az üzleti transzformációt.

## A javaslatunk: Org Pondus
A koncepciónk neve **Org Pondus** volt: egy AI-ügynökökre és súlyozott gráfra épülő szoftver szervezetek fejlesztésére és védelmére.

A kiinduló probléma az volt, hogy sok szervezet még mindig nem rendelkezik adatvezérelt, pontos képpel a saját működéséről, kompetenciáiról és belső struktúrájáról. A hiring, a workforce planning és a kapacitásdöntések gyakran megérzések, töredezett információk vagy szubjektív vezetői benyomások alapján születnek. Nagyvállalati környezetben ez rossz pozícióba felvett emberekhez, rejtett kompetenciahiányokhoz, túlterhelt kulcsterületekhez, alulhasznált csapatokhoz és lassabb organikus növekedéshez vezethet.

Az **Org Pondus** célja egy objektívebb, folyamatosan frissülő szervezeti kép létrehozása volt, amely több forrást kapcsol össze:
- Meglévő vállalati tudásbázisok és belső dokumentációk
- HR- és ticketing rendszerek eseményei
- Releváns publikus és piaci adatok
- Súlyozott szervezeti gráf
- Specializált AI-ügynökök hiring, workforce planning és stratégiai értékelés támogatására

A cél nem a vezetői döntések kiváltása volt, hanem egy jobb tényalap biztosítása. A rendszer azt segítené megérteni, hol hiányzik kapacitás, mely csapatok túlterheltek, mely kompetenciák stratégiai fontosságúak, és mikor érdemes hiring, átszervezés vagy megtartási lépések irányába mozdulni.

## Technikai irány
A technikai javaslat egy ágens-alapú, felhőben futó architektúra volt, referencia-megvalósításként AWS környezetre tervezve.

![Org Pondus ágensrendszer](/images/pwc-hackathon-2026-agent-system.png)

A design középpontjában az **Amazon Bedrock AgentCore Runtime** állt, amely több specializált ügynököt koordinálna:
- **Hiring Manager Agent** pozíciódefiníciókhoz és hiring javaslatokhoz
- **Organization Tree Balancing Agent** kapacitás- és struktúraelemzéshez
- **Organization Strategy Evaluator Agent** stratégiai döntések értékeléséhez
- **Workforce Decisionmaker Agentek** operatív döntéstámogatáshoz

Az ügynökök **AgentCore Gateway** rétegen keresztül kapcsolódnának vállalati rendszerekhez és tudásforrásokhoz, például ticketing rendszerekhez, LinkedInhez, Hayshez, belső tudásbázisokhoz és szervezeti adatokhoz. A **Bedrock Knowledge Base** és az **Amazon Neptune** gráfréteg együtt adná a szemantikus tudást és a strukturált szervezeti kapcsolatokat.

![Org Pondus magas szintű architektúra](/images/pwc-hackathon-2026-high-level-architecture.png)

A magas szintű architektúra fő elemei:
- **Route 53, CloudFront, S3, API Gateway, WAF és Lambda** egy serverless webes és API réteghez
- **EventBridge** HR- és ticketing események közel valós idejű feldolgozásához
- **Bedrock AI modellek** következtetéshez, ajánlásokhoz és természetes nyelvű interakcióhoz
- **Bedrock AgentCore Runtime** az ágensrendszer orchestration rétegéhez
- **Bedrock Knowledge Base** vállalatspecifikus tudás visszakereséséhez
- **Amazon Neptune** a súlyozott szervezeti gráfhoz
- **MCP-jellegű integrációk** Jira, Hays, LinkedIn és belső rendszerek felé

Terveztünk egy frontendet is, amely vizualizálja a szervezeti gráfot, kiemeli a kritikus gyengeségeket és erősségeket, valamint lehetőséget ad stratégiai prioritások beállítására, hogy a rendszer ajánlásai a cég céljaihoz igazodjanak.

## Üzleti érték és ROI
Az üzleti érték a hiring, a megtartás és a szervezeti tervezés mérhető javítására épült.

SaaS és usage-alapú árazási modellt javasoltunk, kezdetben adatgazdag tech cégekre fókuszálva, később KKV és enterprise irányba skálázva. A pitchben egy első, productionben is használható iteráció kezdeti fejlesztési költségét körülbelül **15 000 euróra** becsültük, amelyet infrastruktúra-, modellhasználati-, support- és sales-költségek követnének.

A várható ügyfélérték:
- Gyorsabb és olcsóbb hiring folyamatok
- Alacsonyabb fluktuáció korábbi kockázatészleléssel
- Kiegyensúlyozottabb workload és kapacitáselosztás
- Objektívebb capacity planning
- Tisztább kép a szervezet erősségeiről és gyenge pontjairól
- Folyamatos riport, predikció és döntéstámogatás valós adatok alapján

Az ötlet ambiciózus volt, de szándékosan földközeli: MVP-vel kezdeni, alfa tesztelésre nyitott cégekkel validálni, majd fokozatosan mélyíteni az integrációkat.

## Mit vittem magammal
Bár nem jutottunk be a legjobb 15 csapat közé, büszke vagyok a koncepcióra. A formátum arra kényszerített minket, hogy ne csak demóban gondolkodjunk, hanem megvalósíthatóságban, ROI-ban, implementációs tervben és enterprise adoptációban is.

Köszönöm a **PwC-nek** az esemény megszervezését és azt, hogy teret adott a technológiai és üzleti gondolkodás találkozásának. Külön köszönöm **Erdős Péter Zsombornak** és **Vargha Bendegúz Attilának** a csapatmunkát, energiát és őszinte szakmai vitákat, amelyek formálták a javaslatot.

Ez az esemény jó emlékeztető volt arra, hogy egy hackathon akkor is lehet sikeres, ha nem végződik döntős helyezéssel: ha jobb ötletet, élesebb gondolkodást és értékes szakmai kapcsolatokat ad, már megérte.
