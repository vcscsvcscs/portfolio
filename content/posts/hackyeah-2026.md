+++
draft = false
date = 2026-10-04T22:00:00+02:00
title = "HackYeah 2026: Pomóc and the Smart City Challenge"
summary = "With our team from Apexlab I spent 24 hours at HackYeah in TAURON Arena Kraków building Pomóc, a civic mesh for neighbourhood sharing on an ordinary day and for emergency messages when the mobile network goes dark."
tags = ["hackathon", "smart-city", "civic-tech", "mesh", "ai", "krakow","poc","simulation","dual-use"]
categories = ["hackathons"]
+++

## HackYeah 2026

**October 3–4, 2026**  
**TAURON Arena Kraków**  
24-hour on-site hackathon · the biggest stationary hackathon in Europe · 3000 participants · teams of 1 to 6 · every participant 18+

I spent the weekend at **HackYeah 2026** with **Fábi Tamás** and **Magyar Dániel**. We competed as **Apexlab** on the **Smart City** open task.

![The Apexlab team at HackYeah 2026](/images/hackyeah-2026-team.jpg)

HackYeah is a 24-hour hackathon where teams take a real brief, build a working prototype, and sit with mentors, partners and the rest of the community. Coding started on Saturday at 11:00. The room is a concert arena, and the scale is what you notice first: the floor, the rigging, and the number of teams building in the same hall.

## The challenge

Cities are already running near the limit of their infrastructure. Populations keep growing, and mobility, energy, transport and access to information all have to work faster and more reliably than they used to.

The Smart City task asked for a tool, an application or a prototype that helps a city work better in everyday conditions. Mobility, resource management, communication with citizens, crisis response, urban data, public services, quality of life: any of those was in scope, as long as the result addressed a real problem. The direction was clear. Build technology that makes ordinary life in a city easier. The category prize pool was **5 000 PLN**.

## Pomóc

Our answer was **Pomóc**, a civic proximity network that runs on devices a city already has.

The failure looks like two failures. On a normal Tuesday, a drill sees about 13 minutes of use in its whole lifetime, and an AED can hang on a wall about 80 metres from a cardiac arrest. On a bad day, the mobile network is often the first thing to drop, and help that already exists nearby cannot be reached. Both are routing problems on the same graph: who is physically near whom.

Pomóc keeps one protocol, one identity and two rule sets.

In **peace mode** it is a hyperlocal sharing network. Borrow a drill, ask who has a spare car seat, hand over a parking spot. Reach is hop-limited, so the request stays in the neighbourhood by design. Sharing is free by default. A lender may ask for a small fee for a loan, the borrower sees it before accepting, and the two people settle directly. Pomóc only shows the fee.

In **emergency mode** the same identities and the same devices carry signed messages after the operator network is gone. Home routers mesh over Wi-Fi. Phones relay over Bluetooth LE. Official alerts, "I am OK" check-ins and life-critical requests, such as an AED, an EpiPen or a fire, keep moving hop by hop. With store-and-forward, a person walking between two islands of the mesh carries the message across the gap.

Emergency mode has three levels, because a cell outage and an armed attack should follow different rules.

| | L1 Disruption | L2 Disaster | L3 Security |
|---|---|---|---|
| Typical cause | Cell outage, cable cut, cyberattack | Flood, storm, long blackout | Armed attack, hybrid threat |
| Who can enter it | Local automation, or a signed declaration | Signed local-authority declaration | Signed local-authority declaration |
| What citizens can send | Life-critical, safety, check-in, local info | The same, plus structured requests through the router portal | Life-critical, safety, check-in. Local info is off |

Jamming the cells can force L1 at most. L2 and L3 need a signature. Under L3, phones stop gossiping their neighbour lists, so the mesh stays a way to ask for help and does not become a live map of where people are.

Trust is standard public-key infrastructure with a civic root. The phone generates its key inside the secure chip, and the private key stays there. The person proves who they are through a national identity wallet, mObywatel in Poland or an EUDI wallet elsewhere. The authority signs a short-lived citizen certificate. Any node can verify a message offline, because the authority root key is already in the app. Routers hold relay certificates only. They forward traffic, and a request signed with a relay certificate is dropped. That constraint is cryptographic.

![How Pomóc fits together: the authority, ISP routers as the backbone, and phones at the edge](/images/hackyeah-2026-architecture.png)

Pomóc, as a full civic system, is a vision. In 24 hours we built the argument for it: an interactive simulation of the protocol on a real piece of the city.

## What you can play

The demo is a browser simulation of Kraków around the bend of the Vistula: Kazimierz, Stradom, Stare Podgórze, Dębniki, Grzegórzki and Zabłocie. Seed 42 always loads that map, so a rehearsed run replays exactly. Phones walk, cycle and drive on the street graph. Routers stand in the blocks between the streets. The river and the parks stay clear.

From the panel you can drop the mobile network, cut the power grid, declare L1, L2 or L3, broadcast an official alert, send a citizen request, accept one, and inject a forged request that every neighbour drops. Packets move one hop per tick, so flooding, hop limits, duplicates, expiry and store-and-forward are all visible on the map. A dashboard counts who is still reachable, delivery by message class, and why a packet was discarded.

![The Pomóc simulation during an L1 power-grid disruption in Kazimierz](/images/hackyeah-2026-sim.png)

The live demo is at [pomoc.varghacsongor.hu](https://pomoc.varghacsongor.hu/). A walkthrough of the same run is on [YouTube](https://youtu.be/VvQO707MbZQ).

The rules live in a pure TypeScript engine. React and Mantine draw the map and the controls. In the simulation, cryptography is a trust flag on the signer, and the protocol timers are compressed so a power cut and a mode change show up within a minute. The demo is about mesh behaviour: who can still hear whom when the cells go down and the routers without a battery go dark.

## Same plan, two model pairs

Alongside the build we ran a small comparison.

We wrote the execution plan with **Claude Fable 5.1** in Ultramode, then carried that same plan out twice. One run used **Fable 5.1** with **Opus** agents. The other used **Sonnet 5.5** with **Haiku** agents.

The interesting part was how much of the quality already lived in the plan. Both runs finished with a working product. The Fable and Opus version was the more refined of the two, and it came out more feature-rich. The Sonnet and Haiku version still looked sound and did the job. The distance between them was smaller than I expected. As a budget pair, Sonnet and Haiku were comparable, because they were executing a plan that Fable had already made very concrete. The stronger pair took the same instructions and pushed the result from solid to exceptional.

## The arena, and Kraków

![The HackYeah floor in TAURON Arena Kraków](/images/hackyeah-2026-arena.jpg)

This was my first hackathon inside a venue like this. The hall, the light and the density of teams made the 24 hours feel like a festival that happened to be about software.

![HackYeah under the arena lights](/images/hackyeah-2026-arena-lights.jpg)

The Polish IT scene left a strong impression. It is well developed, and it is vibrant. I had time to talk to people beyond our own table, and those conversations were a real part of the weekend.

![Outside TAURON Arena Kraków](/images/hackyeah-2026-tauron-arena.jpg)

Kraków matched the event. It is a beautiful city, and the food was excellent.

One detail from the floor is going to stay with me. The organisers handed out an energy shot, Strzał Energii: **200 mg of caffeine in 120 ml**. That is a lot of caffeine in a very small bottle.

![The 120 ml energy shot from the hackathon](/images/hackyeah-2026-energy-shot.jpg)

We did not reach the finals. I am proud of the team, and of what we made. Tom and Dani were wonderful teammates. We worked on the idea with real passion, kept pressure on the design until it held together, and left with a demo I am happy to show.

Being in the room for the largest stationary hackathon in Europe is an experience I will not forget.

[Play the simulation](https://pomoc.varghacsongor.hu/) · [Watch the video](https://youtu.be/VvQO707MbZQ)
