+++
draft = false
date = 2026-04-16T00:00:00+02:00
title = "PwC Hackathon 2026: Org Pondus ja tekoälypohjainen organisaatiosuunnittelu"
summary = "Tiimini ja minä osallistuimme PwC Hackathon 2026 -tapahtumaan Org Pondus -konseptilla: tekoälyagentteihin ja painotettuun graafiin perustuvalla ratkaisulla datavetoiseen rekrytointiin, workforce planningiin, henkilöstön pysyvyyteen ja organisaatiostrategiaan."
tags = ["hackathon", "pwc", "ai", "agents", "aws", "bedrock", "agentcore", "knowledge-graph", "hr-tech"]
categories = ["hackathons"]
+++

## PwC Hackathon 2026
**16. huhtikuuta 2026**  
**PwC Unkari, Budapest**  
Esikarsinta • liiketoimintakonseptin pitch • MVP canvas • ROI-suunnittelu • hackathonin toteutussuunnitelma

Tiimini ja minä osallistuimme **PwC Hackathon 2026** -tapahtumaan, joka oli korkean profiilin ja rakenteeltaan poikkeuksellinen hackathon Budapestissa. Tiimissäni olivat **Erdős Péter Zsombor** ja **Vargha Bendegúz Attila**, veljeni, ja tiiminimenämme oli **The Professionals**.

Tapahtuma erosi monista muista hackathoneista. Ennen varsinaista finaalivaihetta tiimien piti läpäistä esikarsinta ja valmistella vakavasti otettava pitch-kokonaisuus: **6-8 dian liiketoimintakonsepti**, **MVP canvas**, **ROI-malli** ja realistinen **hackathonin toteutussuunnitelma**. Emme valitettavasti päässeet 15 finaalitiimin joukkoon, mutta kokemus oli silti erittäin arvokas. Rakensimme merkityksellisen ehdotuksen, terävöitimme sitä paineen alla ja loimme hyviä ammatillisia yhteyksiä.

![The Professionals -tiimi PwC Hackathon 2026 -tapahtumassa](/images/pwc-hackathon-2026-team.png)

Yksi tärkeimmistä hetkistä oli mahdollisuus keskustella PwC Unkarin johdon kanssa sekä käydä teknisiä keskusteluja Cloud Engineering- ja AI Engineering -johtajien kanssa. Se teki tapahtumasta paljon enemmän kuin kilpailun: se oli myös harvinainen mahdollisuus validoida ideaa ihmisten kanssa, jotka ymmärtävät sekä enterprise-teknologiaa että liiketoiminnan muutosta.

## Ehdotuksemme: Org Pondus
Konseptimme nimi oli **Org Pondus**: tekoälyagentteihin ja painotettuun graafiin perustuva alusta organisaatioiden kehittämiseen ja suojaamiseen.

Lähtökohtainen ongelma oli, että monet organisaatiot tekevät edelleen rekrytointiin, workforce planningiin ja sisäisiin kyvykkyyksiin liittyviä päätöksiä ilman selkeää, dataan perustuvaa karttaa omasta rakenteestaan. Päätökset pohjautuvat usein intuitioon, hajanaiseen tietoon tai subjektiivisiin johtamisnäkemyksiin. Suurissa yrityksissä tämä voi johtaa vääriin rekrytointeihin, piilossa oleviin osaamisaukkoihin, ylikuormittuneisiin avaintiimeihin, alihyödynnettyihin osastoihin ja hitaampaan orgaaniseen kasvuun.

**Org Pondus** oli suunniteltu luomaan objektiivisempi ja jatkuvasti päivittyvä kuva organisaatiosta yhdistämällä:
- Olemassa olevat yrityksen tietopohjat ja sisäinen dokumentaatio
- HR- ja ticketing-järjestelmien tapahtumat
- Tarvittaessa julkinen ja markkinadata
- Painotettu organisaatiograafi
- Erikoistuneet tekoälyagentit rekrytointiin, workforce planningiin ja strategiseen arviointiin

Tavoitteena ei ollut korvata johdon harkintaa. Tarkoitus oli antaa johdolle, HR-tiimeille ja managereille parempi faktapohja: missä kapasiteettia puuttuu, mitkä tiimit ovat ylikuormittuneita, mitkä osaamiset ovat strategisesti tärkeitä ja milloin kannattaa rekrytoida, tasapainottaa tiimejä tai panostaa henkilöstön pysyvyyteen.

## Tekninen suunta
Tekninen ehdotus oli agenttipohjainen pilviarkkitehtuuri, jossa AWS toimi referenssitoteutuksena.

![Org Pondus -agenttijärjestelmä](/images/pwc-hackathon-2026-agent-system.png)

Suunnittelun keskellä oli **Amazon Bedrock AgentCore Runtime**, joka koordinoisi useita erikoistuneita agentteja:
- **Hiring Manager Agent** roolien määrittelyyn ja rekrytointisuosituksiin
- **Organization Tree Balancing Agent** kapasiteetti- ja rakenneanalyysiin
- **Organization Strategy Evaluator Agent** strategisten vaihtoehtojen arviointiin
- **Workforce Decisionmaker Agents** operatiiviseen päätöksentukeen

Nämä agentit yhdistyisivät **AgentCore Gateway** -kerroksen kautta yritysjärjestelmiin ja tietolähteisiin, kuten ticketing-työkaluihin, LinkedIniin, Haysiin, sisäisiin tietopohjiin ja organisaatiodataan. **Bedrock Knowledge Base** ja **Amazon Neptune** -graafikerros tarjoaisivat sekä semanttisen tiedon että rakenteelliset organisaatiosuhteet.

![Org Pondus -korkean tason arkkitehtuuri](/images/pwc-hackathon-2026-high-level-architecture.png)

Ehdotettu korkean tason arkkitehtuuri sisälsi:
- **Route 53, CloudFront, S3, API Gateway, WAF ja Lambda** serverless web- ja API-kerrokseen
- **EventBridge** HR- ja ticketing-tapahtumien lähes reaaliaikaiseen käsittelyyn
- **Bedrock AI -mallit** päättelyyn, suosituksiin ja luonnollisen kielen vuorovaikutukseen
- **Bedrock AgentCore Runtime** agenttijärjestelmän orkestrointiin
- **Bedrock Knowledge Base** yrityskohtaisen tiedon hakemiseen
- **Amazon Neptune** painotettuun organisaatiograafiin
- **MCP-tyyliset integraatiot** Jiraan, Haysiin, LinkedIniin ja sisäisiin järjestelmiin

Suunnittelimme myös käyttöliittymän, joka visualisoisi organisaatiograafin, nostaisi esiin kriittiset vahvuudet ja heikkoudet sekä mahdollistaisi strategisten prioriteettien määrittelyn, jotta järjestelmän suositukset olisivat linjassa yrityksen tavoitteiden kanssa.

## Liiketoiminta-arvo ja ROI
Liiketoimintamalli keskittyi mitattaviin parannuksiin rekrytoinnissa, henkilöstön pysyvyydessä ja organisaatiosuunnittelussa.

Ehdotimme SaaS- ja käyttöperusteista hinnoittelua, aluksi datarikkaille teknologiayrityksille ja myöhemmin pk-yrityksiin sekä enterprise-asiakkaisiin skaalaten. Pitchissä arvioimme ensimmäisen tuotantokelpoisen version alkuinvestoinniksi noin **15 000 euroa**, minkä jälkeen kuukausikustannukset riippuisivat infrastruktuurista, mallien käytöstä, supportista ja myynnistä.

Odotettu asiakasarvo:
- Nopeammat ja edullisemmat rekrytointiprosessit
- Pienempi vaihtuvuus riskien aikaisemman havaitsemisen avulla
- Tasapainoisempi työkuorman ja kapasiteetin jakautuminen
- Objektiivisempi kapasiteettisuunnittelu
- Selkeämpi näkyvyys organisaation vahvuuksiin ja heikkouksiin
- Jatkuva raportointi, ennustaminen ja päätöksentuki todellisen datan perusteella

Idea oli kunnianhimoinen, mutta tarkoituksella käytännönläheinen: aloittaa MVP:llä, validoida se alpha-testaukseen avoimien yritysten kanssa ja syventää integraatioita vaiheittain.

## Mitä opin
Vaikka emme päässeet 15 finalistin joukkoon, olen ylpeä konseptista. Formaatti pakotti meidät ajattelemaan demoa pidemmälle: toteutettavuutta, ROI:ta, implementointisuunnitelmaa ja enterprise-adoptiota heti alusta alkaen.

Kiitos **PwC:lle** tapahtuman järjestämisestä ja tilan luomisesta, jossa tekninen ja liiketoiminnallinen ajattelu kohtasivat. Kiitos myös **Erdős Péter Zsomborille** ja **Vargha Bendegúz Attilalle** tiimityöstä, energiasta ja rehellisistä keskusteluista, jotka muovasivat ehdotusta.

Tämä oli hyvä muistutus siitä, että hackathon voi olla onnistunut myös ilman finaalipaikkaa, jos se tuottaa paremman idean, terävämpää ajattelua ja merkityksellisiä ammatillisia suhteita.
