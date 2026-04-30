+++
draft = false
date = 2026-04-16T00:00:00+02:00
title = "PwC Hackathon 2026: Org Pondus und KI-gestützte Organisationsentwicklung"
summary = "Mein Team und ich nahmen am PwC Hackathon 2026 teil und präsentierten Org Pondus: ein Konzept mit KI-Agenten und gewichteten Graphen für datengetriebenes Hiring, Workforce Planning, Retention und Organisationsstrategie."
tags = ["hackathon", "pwc", "ki", "agents", "aws", "bedrock", "agentcore", "knowledge-graph", "hr-tech"]
categories = ["hackathons"]
+++

## PwC Hackathon 2026
**16. April 2026**  
**PwC Ungarn, Budapest**  
Vorauswahl • Business-Concept-Pitch • MVP Canvas • ROI-Planung • Hackathon-Umsetzungsplan

Mein Team und ich nahmen am **PwC Hackathon 2026** teil, einem hochkarätigen und ungewöhnlich strukturierten Hackathon in Budapest. Ich arbeitete mit **Erdős Péter Zsombor** und **Vargha Bendegúz Attila**, meinem Bruder, unter dem Teamnamen **The Professionals** zusammen.

Der Ablauf unterschied sich deutlich von vielen anderen Hackathons. Vor der eigentlichen Finalrunde mussten Teams zuerst eine Vorauswahl bestehen und anschließend ein ernsthaftes Pitch-Paket vorbereiten: ein **6-8 Folien umfassendes Business-Konzept**, ein **MVP Canvas**, ein **ROI-Modell** und einen realistischen **Hackathon-Arbeitsplan**. Wir schafften es leider nicht unter die 15 Finalteams, aber die Erfahrung war trotzdem sehr wertvoll. Wir entwickelten ein bedeutungsvolles Konzept, schärften es unter Druck und knüpften wichtige professionelle Kontakte.

![The Professionals Team beim PwC Hackathon 2026](/images/pwc-hackathon-2026-team.png)

Ein persönliches Highlight war die Möglichkeit, mit der Führung von PwC Ungarn zu sprechen und technische Gespräche mit den Leitern für Cloud Engineering und AI Engineering zu führen. Dadurch fühlte sich die Veranstaltung nicht nur wie ein Wettbewerb an, sondern auch wie eine seltene Gelegenheit, eine Idee mit Menschen zu validieren, die Enterprise-Technologie und Business Transformation wirklich verstehen.

## Unser Vorschlag: Org Pondus
Unser Konzept hieß **Org Pondus**: eine Plattform auf Basis von KI-Agenten und gewichteten Graphen zur Entwicklung und zum Schutz von Organisationen.

Das zentrale Problem: Viele Unternehmen treffen Entscheidungen zu Hiring, Workforce Planning und internen Fähigkeiten noch immer ohne eine klare, datengetriebene Karte ihrer eigenen Organisation. Entscheidungen entstehen oft aus Intuition, fragmentierten Informationen oder subjektiven Management-Eindrücken. In großen Unternehmen kann das zu falschen Einstellungen, versteckten Kompetenzlücken, überlasteten Schlüsselteams, ungenutzten Bereichen und langsamerem organischem Wachstum führen.

**Org Pondus** sollte ein objektiveres, kontinuierlich aktualisiertes Bild der Organisation schaffen, indem mehrere Quellen verbunden werden:
- Bestehende Wissensdatenbanken und interne Dokumentation
- Ereignisse aus HR- und Ticketing-Systemen
- Relevante öffentliche und Marktdaten
- Ein gewichteter Organisationsgraph
- Spezialisierte KI-Agenten für Hiring, Workforce Planning und strategische Bewertung

Das Ziel war nicht, Führungsentscheidungen zu ersetzen. Die Plattform sollte Führungskräften, HR-Teams und Managern eine bessere Faktenbasis geben: wo Kapazitäten fehlen, welche Teams überlastet sind, welche Fähigkeiten strategisch wichtig sind und wann Hiring, Rebalancing oder Retention-Maßnahmen sinnvoll werden.

## Technische Richtung
Der technische Vorschlag war eine agentenbasierte Cloud-Architektur mit AWS als Referenzumgebung.

![Org Pondus Agentensystem](/images/pwc-hackathon-2026-agent-system.png)

Im Zentrum stand **Amazon Bedrock AgentCore Runtime**, das mehrere spezialisierte Agenten koordinieren würde:
- **Hiring Manager Agent** für Rollendefinitionen und Hiring-Empfehlungen
- **Organization Tree Balancing Agent** für Kapazitäts- und Strukturanalysen
- **Organization Strategy Evaluator Agent** für strategische Trade-off-Bewertungen
- **Workforce Decisionmaker Agents** für operative Entscheidungsunterstützung

Über **AgentCore Gateways** würden diese Agenten mit Enterprise-Systemen und Wissensquellen verbunden, etwa Ticketing-Tools, LinkedIn, Hays, internen Wissensdatenbanken und Organisationsdaten. Eine **Bedrock Knowledge Base** und ein **Amazon Neptune** Graph-Layer würden semantisches Wissen und strukturierte Organisationsbeziehungen kombinieren.

![High-Level-Architektur von Org Pondus](/images/pwc-hackathon-2026-high-level-architecture.png)

Die vorgeschlagene Architektur umfasste:
- **Route 53, CloudFront, S3, API Gateway, WAF und Lambda** für eine serverlose Web- und API-Schicht
- **EventBridge** für die nahezu echtzeitfähige Verarbeitung von HR- und Ticketing-Events
- **Bedrock AI Models** für Reasoning, Empfehlungen und natürliche Sprachinteraktion
- **Bedrock AgentCore Runtime** zur Orchestrierung des Agentensystems
- **Bedrock Knowledge Base** für unternehmensspezifisches Retrieval
- **Amazon Neptune** für den gewichteten Organisationsgraphen
- **MCP-ähnliche Integrationen** zu Jira, Hays, LinkedIn und internen Systemen

Zusätzlich planten wir ein Frontend, das den Organisationsgraphen visualisiert, kritische Stärken und Schwächen hervorhebt und strategische Prioritäten konfigurierbar macht.

## Business Value und ROI
Der Business Case konzentrierte sich auf messbare Verbesserungen in Hiring, Retention und Organisationsplanung.

Wir schlugen ein SaaS- und usage-basiertes Preismodell vor, zuerst für datenreiche Technologieunternehmen und später skalierbar für KMU und Enterprise-Kunden. Für eine erste production-taugliche Iteration schätzten wir eine Anfangsinvestition von etwa **15.000 EUR**, gefolgt von laufenden Kosten für Infrastruktur, Modellnutzung, Support und Sales.

Der erwartete Kundennutzen:
- Schnellere und günstigere Hiring-Prozesse
- Geringere Fluktuation durch frühere Risikoerkennung
- Besser ausbalancierte Arbeitslast und Kapazitätsplanung
- Objektivere Workforce-Entscheidungen
- Klarere Sicht auf organisatorische Stärken und Schwächen
- Kontinuierliche Reports, Prognosen und Entscheidungshilfen auf Basis realer Daten

Die Idee war ambitioniert, aber bewusst bodenständig: mit einem MVP starten, mit alpha-testbereiten Unternehmen validieren und Integrationen schrittweise vertiefen.

## Mein Fazit
Auch wenn wir nicht unter die besten 15 Teams kamen, bin ich stolz auf das Konzept. Das Format zwang uns, nicht nur über eine Demo nachzudenken, sondern auch über Machbarkeit, ROI, Implementierungsplanung und Enterprise Adoption.

Vielen Dank an **PwC** für die Organisation und dafür, einen Raum zu schaffen, in dem technisches und geschäftliches Denken zusammenkommen konnten. Danke auch an **Erdős Péter Zsombor** und **Vargha Bendegúz Attila** für Teamwork, Energie und ehrliche fachliche Diskussionen.

Der Hackathon war eine gute Erinnerung daran, dass ein Event auch ohne Finalplatzierung erfolgreich sein kann, wenn daraus eine bessere Idee, klareres Denken und wertvolle professionelle Beziehungen entstehen.
