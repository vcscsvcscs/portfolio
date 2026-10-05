+++
draft = false
date = 2026-10-04T22:00:00+02:00
title = "HackYeah 2026: Pomóc und die Smart-City-Challenge"
summary = "Mit dem Team von Apexlab arbeitete ich 24 Stunden beim HackYeah in der TAURON Arena Kraków an Pomóc, einem zivilen Mesh fürs Teilen in der Nachbarschaft an einem gewöhnlichen Tag und für Notfallnachrichten, wenn das Mobilfunknetz ausfällt."
tags = ["hackathon", "smart-city", "civic-tech", "mesh", "ai", "krakow","poc","simulation","dual-use"]
categories = ["hackathons"]
+++

## HackYeah 2026
**3.–4. Oktober 2026**  
**TAURON Arena Kraków**  
24-Stunden-Hackathon vor Ort · der größte Präsenz-Hackathon Europas · 3000 Teilnehmende · Teams von 1 bis 6 · Teilnahme ab 18

Das Wochenende verbrachte ich beim **HackYeah 2026** mit **Fábi Tamás** und **Magyar Dániel**. Als **Apexlab** traten wir bei der offenen Aufgabe **Smart City** an.

![Das Team Apexlab beim HackYeah 2026](/images/hackyeah-2026-team.jpg)

HackYeah ist ein 24-Stunden-Hackathon: Teams bekommen eine echte Aufgabenstellung, bauen einen funktionierenden Prototyp und sitzen mit Mentoren, Partnern und dem Rest der Community in einem Raum. Am Samstag um 11:00 Uhr ging das Coden los. Der Raum ist eine Konzertarena, und als Erstes fällt auf, wie groß das Ganze ist: der Boden, die Traversen und die Zahl der Teams, die in derselben Halle bauen.

## Die Aufgabe

Städte stoßen schon jetzt an die Grenzen ihrer Infrastruktur. Die Bevölkerung wächst, und Mobilität, Energie, Verkehr und der Zugang zu Informationen müssen schneller und zuverlässiger funktionieren als früher.

Die Smart-City-Aufgabe verlangte ein Werkzeug, eine Anwendung oder einen Prototyp, der einer Stadt im Alltag hilft, besser zu funktionieren. Mobilität, Ressourcen, Kommunikation mit den Bürgern, Krisenreaktion, städtische Daten, öffentliche Dienstleistungen, Lebensqualität: all das war zulässig, solange das Ergebnis ein echtes Problem anging. Die Richtung war klar: Es ging um Technik, die den Alltag in der Stadt leichter macht. Das Preisgeld der Kategorie lag bei **5 000 PLN**.

## Pomóc

Unsere Antwort war **Pomóc**, ein ziviles Mesh für die unmittelbare Nähe. Es läuft auf Geräten, die eine Stadt schon hat.

Auf den ersten Blick sind es zwei verschiedene Arten von Versagen. An einem normalen Dienstag ist eine Bohrmaschine in ihrem ganzen Leben nur etwa 13 Minuten in Gebrauch, und ein Defibrillator kann 80 Meter von einem Herzstillstand entfernt an der Wand hängen. An einem schlechten Tag fällt das Mobilfunknetz oft als Erstes aus, und Hilfe, die es in der Nähe schon gibt, ist nicht erreichbar. Beides sind Routing-Probleme auf demselben Graphen: wer physisch bei wem ist.

Pomóc hat ein Protokoll, eine Identität und zwei Regelsätze.

Im **Friedensmodus** ist es ein Netz zum Teilen in der unmittelbaren Nachbarschaft. Man leiht eine Bohrmaschine, fragt, wer einen Kindersitz übrig hat, und gibt einen Parkplatz weiter. Die Reichweite ist in Hops begrenzt, deshalb bleibt die Anfrage von vornherein im Viertel. Teilen ist im Normalfall kostenlos. Wer verleiht, darf eine kleine Gebühr verlangen. Wer leiht, sieht sie, bevor er annimmt. Die beiden rechnen direkt miteinander ab. Pomóc zeigt nur die Gebühr.

Im **Notfallmodus** befördern dieselben Identitäten und dieselben Geräte signierte Nachrichten, sobald das Netz des Mobilfunkbetreibers weg ist. Heimrouter bilden ein Mesh über WLAN. Telefone leiten über Bluetooth LE weiter. Amtliche Warnungen, „Mir geht es gut“-Meldungen und lebenswichtige Anfragen, etwa zu einem Defibrillator, einem EpiPen oder einem Brand, wandern Hop für Hop. Mit Store-and-Forward trägt jemand, der zwischen zwei Inseln des Netzes zu Fuß unterwegs ist, die Nachricht über die Lücke.

Der Notfallmodus hat drei Stufen, weil ein Funkzellenausfall und ein bewaffneter Angriff nicht nach denselben Regeln ablaufen sollen.

| | L1 Störung | L2 Katastrophe | L3 Sicherheit |
|---|---|---|---|
| Typische Ursache | Funkzellenausfall, Kabelbruch, Cyberangriff | Hochwasser, Sturm, langer Blackout | Bewaffneter Angriff, hybride Bedrohung |
| Wer ihn auslösen kann | Lokale Automatisierung oder eine signierte Erklärung | Signierte Erklärung der lokalen Behörde | Signierte Erklärung der lokalen Behörde |
| Was Bürger senden können | Lebenswichtig, Sicherheit, Check-in, lokale Info | Dasselbe, dazu strukturierte Anfragen über das Router-Portal | Lebenswichtig, Sicherheit, Check-in. Lokale Info ist abgeschaltet |

Wer die Funkzellen stört, kann höchstens L1 erzwingen. L2 und L3 brauchen eine Signatur. Unter L3 geben die Telefone ihre Nachbarlisten nicht mehr weiter. So bleibt das Mesh ein Weg, Hilfe zu rufen, und wird keine Live-Karte, die zeigt, wo sich Menschen aufhalten.

Das Vertrauen beruht auf einer ganz normalen Public-Key-Infrastruktur mit einer zivilen Wurzel. Das Telefon erzeugt seinen Schlüssel im Secure Element, und der private Schlüssel bleibt dort. Die Person weist sich über eine nationale Identitäts-Wallet aus: mObywatel in Polen, eine EUDI-Wallet anderswo. Die Behörde signiert ein kurzlebiges Bürgerzertifikat. Jeder Knoten kann eine Nachricht offline prüfen, weil der Root-Key der Behörde schon in der App steckt. Router haben nur Relay-Zertifikate. Sie leiten Verkehr weiter, und eine Anfrage, die mit einem Relay-Zertifikat signiert ist, wird verworfen. Diese Grenze ist kryptografisch abgesichert.

![So hängt Pomóc zusammen: die Behörde, die Router der Internetanbieter als Rückgrat, die Telefone am Rand](/images/hackyeah-2026-architecture.png)

Pomóc als volles städtisches System ist eine Vision. In 24 Stunden bauten wir das, was dafür spricht: eine interaktive Simulation des Protokolls auf einem echten Stück Stadt.

## Was sich ausprobieren lässt

Die Demo ist eine Browsersimulation von Kraków an der Biegung der Weichsel: Kazimierz, Stradom, Stare Podgórze, Dębniki, Grzegórzki und Zabłocie. Seed 42 lädt immer diese Karte, deshalb lässt sich ein geprobter Durchlauf exakt wiederholen. Telefone gehen, radeln und fahren auf dem Straßengraphen. Router stehen in den Häuserblöcken zwischen den Straßen. Der Fluss und die Parks bleiben frei.

Über das Panel lässt sich das Mobilfunknetz abschalten, das Stromnetz kappen, L1, L2 oder L3 ausrufen, eine amtliche Warnung senden, eine Bürgeranfrage schicken, eine annehmen und eine gefälschte Anfrage einschleusen, die jeder Nachbar verwirft. Pakete kommen pro Tick einen Hop weiter, deshalb sieht man Paketfluten, Hop-Limits, Duplikate, ablaufende Pakete und Store-and-Forward auf der Karte. Ein Dashboard zeigt, wer noch erreichbar ist, die Zustellung nach Nachrichtenklasse und warum ein Paket verworfen wurde.

![Die Pomóc-Simulation bei einer L1-Störung des Stromnetzes in Kazimierz](/images/hackyeah-2026-sim.png)

Die Live-Demo ist unter [pomoc.varghacsongor.hu](https://pomoc.varghacsongor.hu/) erreichbar. Denselben Durchlauf gibt es als [Video auf YouTube](https://youtu.be/VvQO707MbZQ).

Die Regeln stecken in einer reinen TypeScript-Engine. React und Mantine zeichnen die Karte und die Steuerung. In der Simulation ist die Kryptografie ein Vertrauensflag am Signierer, und die Protokoll-Timer sind zeitlich gestaucht, damit ein Stromausfall und ein Moduswechsel innerhalb einer Minute sichtbar werden. Die Demo zeigt, wie sich das Mesh verhält: wer noch wen hört, wenn die Funkzellen ausfallen und die Router ohne Batterie dunkel werden.

## Derselbe Plan, zwei Modellpaare

Nebenher ließen wir einen kleinen Vergleich laufen.

Den Ausführungsplan schrieben wir mit **Claude Fable 5.1** im Ultramode und führten denselben Plan dann zweimal aus. Ein Lauf nutzte **Fable 5.1** mit **Opus**-Agenten. Der andere nutzte **Sonnet 5.5** mit **Haiku**-Agenten.

Interessant war, wie viel Qualität schon im Plan steckte. Beide Läufe endeten mit einem funktionierenden Produkt. Die Fassung mit Fable und Opus war die ausgefeiltere und kam funktionsreicher heraus. Die Fassung mit Sonnet und Haiku sah trotzdem stimmig aus und tat, was sie sollte. Der Abstand zwischen beiden war kleiner, als ich erwartet hatte. Als günstigeres Paar waren Sonnet und Haiku nah dran, weil sie einen Plan ausführten, den Fable schon sehr konkret gemacht hatte. Das stärkere Paar bekam dieselben Anweisungen und brachte das Ergebnis vom Soliden zum Außergewöhnlichen.

## Die Arena und Kraków

![Der Hallenboden beim HackYeah in der TAURON Arena Kraków](/images/hackyeah-2026-arena.jpg)

Das war mein erster Hackathon an einem solchen Ort. Die Halle, das Licht und die Dichte der Teams ließen die 24 Stunden wie ein Festival wirken, das zufällig von Software handelte.

![HackYeah im Licht der Arena](/images/hackyeah-2026-arena-lights.jpg)

Die polnische IT-Szene hinterließ einen starken Eindruck. Sie ist weit gekommen, und sie ist lebendig. Ich hatte Zeit, mit Leuten zu sprechen, die nicht an unserem Tisch saßen, und diese Gespräche gehörten wirklich zum Wochenende.

![Vor der TAURON Arena Kraków](/images/hackyeah-2026-tauron-arena.jpg)

Kraków passte zum Hackathon. Es ist eine schöne Stadt, und das Essen war ausgezeichnet.

Ein Detail aus der Halle bleibt hängen. Die Organisatoren verteilten einen Energy-Shot, Strzał Energii: **200 mg Koffein in 120 ml**. Das ist viel Koffein in einer sehr kleinen Flasche.

![Der 120-ml-Energy-Shot vom Hackathon](/images/hackyeah-2026-energy-shot.jpg)

Wir erreichten das Finale nicht. Auf das Team und auf das, was wir gebaut haben, bin ich trotzdem stolz. Tom und Dani waren großartige Teamkollegen. Wir arbeiteten mit echter Leidenschaft an der Idee, setzten den Entwurf so lange unter Druck, bis er hielt, und gingen mit einer Demo, die ich gern zeige.

Im Raum zu sein, beim größten Präsenz-Hackathon Europas, ist eine Erfahrung, die ich nicht vergesse.

[Die Simulation starten](https://pomoc.varghacsongor.hu/) · [Das Video ansehen](https://youtu.be/VvQO707MbZQ)
