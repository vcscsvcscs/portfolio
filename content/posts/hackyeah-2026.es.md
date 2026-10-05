+++
draft = false
date = 2026-10-04T22:00:00+02:00
title = "HackYeah 2026: Pomóc y el reto de Smart City"
summary = "Pasé 24 horas en el HackYeah, en el TAURON Arena Kraków, con el equipo de Apexlab, construyendo Pomóc: una malla cívica para compartir en el barrio un día cualquiera y, cuando cae la red móvil, para los mensajes de emergencia."
tags = ["hackathon", "smart-city", "civic-tech", "mesh", "ai", "krakow","poc","simulation","dual-use"]
categories = ["hackathons"]
+++

## HackYeah 2026
**3 y 4 de octubre de 2026**  
**TAURON Arena Kraków**  
Hackathon presencial de 24 horas · el mayor hackathon presencial de Europa · 3000 participantes

Pasé el fin de semana en el **HackYeah 2026** con **Fábi Tamás** y **Magyar Dániel**. Competimos como **Apexlab** en el reto abierto de **Smart City**.

![El equipo Apexlab en el HackYeah 2026](/images/hackyeah-2026-team.jpg)

HackYeah es un hackathon de 24 horas: los equipos reciben un reto real, construyen un prototipo que funciona y trabajan junto a mentores, socios y el resto de la comunidad. Empezamos a programar el sábado a las 11:00. La sala es un estadio de conciertos, y lo primero que se nota es la escala: el suelo, la estructura de luces y la cantidad de equipos que construyen en el mismo pabellón.

## El reto

Las ciudades ya funcionan al límite de su infraestructura. La población sigue creciendo, y la movilidad, la energía, el transporte y el acceso a la información tienen que funcionar más rápido y con mayor fiabilidad que antes.

El reto de Smart City pedía una herramienta, una aplicación o un prototipo que ayude a una ciudad a funcionar mejor en el día a día. Movilidad, gestión de recursos, comunicación con la ciudadanía, respuesta a crisis, datos urbanos, servicios públicos, calidad de vida: cualquiera de esos temas valía, siempre que el resultado abordara un problema real. La idea era clara. Construir tecnología que facilite la vida cotidiana en una ciudad. El premio de la categoría era de **5 000 PLN**.

## Pomóc

Nuestra respuesta fue **Pomóc**, una red cívica de proximidad que funciona en dispositivos que la ciudad ya tiene.

Parece que son dos fallos. Un martes normal, un taladro se usa unos 13 minutos en toda su vida, y un desfibrilador puede estar colgado en una pared a unos 80 metros de una parada cardíaca. En un mal día, la red móvil suele ser lo primero que cae, y la ayuda que ya hay cerca queda fuera de alcance. Los dos son problemas de encaminamiento sobre el mismo grafo: quién está físicamente cerca de quién.

Pomóc mantiene un único protocolo, una única identidad y dos conjuntos de reglas.

En **modo de paz**, Pomóc es una red para compartir en el barrio. Pedir prestado un taladro, preguntar quién tiene una silla de coche de sobra, ceder una plaza de aparcamiento. El alcance está limitado por saltos, así que la petición se queda en el barrio a propósito. Por defecto, compartir es gratis. Quien presta puede pedir un pequeño importe; quien pide prestado lo ve antes de aceptar, y se pagan directamente entre ellos. Pomóc solo muestra el importe.

En **modo de emergencia**, las mismas identidades y los mismos dispositivos transportan mensajes firmados cuando la red del operador ya ha caído. Los routers de casa forman una malla por Wi-Fi. Los teléfonos reenvían por Bluetooth LE. Las alertas oficiales, los avisos de «estoy bien» y las peticiones vitales —un desfibrilador, un EpiPen, un incendio— siguen avanzando salto a salto. Con store-and-forward, una persona que camina entre dos islas de la malla lleva el mensaje de una a la otra.

El modo de emergencia tiene tres niveles, porque un corte de celdas y un ataque armado no deben seguir las mismas reglas.

| | L1 Interrupción | L2 Desastre | L3 Seguridad |
|---|---|---|---|
| Causa típica | Corte de celdas, cable cortado, ciberataque | Inundación, tormenta, apagón largo | Ataque armado, amenaza híbrida |
| Quién puede activarlo | Automatización local o una declaración firmada | Declaración firmada de la autoridad local | Declaración firmada de la autoridad local |
| Qué puede enviar la ciudadanía | Vital, seguridad, check-in, información local | Lo mismo, y también peticiones estructuradas a través del portal del router | Vital, seguridad, check-in. La información local está desactivada |

El jamming de las celdas solo puede forzar L1. L2 y L3 necesitan una firma. En L3 los teléfonos dejan de intercambiar sus listas de vecinos, así que la malla sigue siendo una forma de pedir ayuda y no se convierte en un mapa en tiempo real de dónde está la gente.

La confianza se apoya en una infraestructura de clave pública estándar, con una raíz cívica. El teléfono genera su clave dentro del chip seguro, y la clave privada se queda ahí. La persona demuestra quién es con una cartera de identidad nacional: mObywatel en Polonia, o una cartera EUDI en otros países. La autoridad firma un certificado de ciudadanía de corta duración. Cualquier nodo puede verificar un mensaje sin conexión, porque la clave raíz de la autoridad ya está en la aplicación. Los routers solo tienen certificados de retransmisión. Reenvían tráfico, y una petición firmada con un certificado de retransmisión se descarta. Ese límite es criptográfico.

![Cómo se articula Pomóc: la autoridad, los routers de los operadores como red troncal y los teléfonos en el borde](/images/hackyeah-2026-architecture.png)

Pomóc, como sistema cívico completo, es una visión. En 24 horas construimos el argumento que la sostiene: una simulación interactiva del protocolo sobre un trozo real de ciudad.

## Lo que se puede probar

La demo es una simulación, en el navegador, de Kraków en el recodo del Vístula: Kazimierz, Stradom, Stare Podgórze, Dębniki, Grzegórzki y Zabłocie. La semilla 42 carga siempre ese mapa, así que un recorrido ensayado se repite tal cual. Los teléfonos caminan, van en bici y conducen sobre el grafo de calles. Los routers están en las manzanas. El río y los parques se quedan libres.

Desde el panel se puede cortar la red móvil, cortar la red eléctrica, declarar L1, L2 o L3, emitir una alerta oficial, enviar una petición ciudadana, aceptar una e inyectar una petición falsa que cada vecino descarta. Los paquetes avanzan un salto por tick, así que el flooding, los límites de salto, los duplicados, la caducidad y el store-and-forward se ven en el mapa. Un cuadro de mando muestra quién sigue siendo alcanzable, la entrega por clase de mensaje y por qué se descartó un paquete.

![La simulación de Pomóc durante una interrupción eléctrica L1 en Kazimierz](/images/hackyeah-2026-sim.png)

La demo en vivo está en [pomoc.varghacsongor.hu](https://pomoc.varghacsongor.hu/). El mismo recorrido se puede ver en [YouTube](https://youtu.be/VvQO707MbZQ).

Las reglas están en un motor de TypeScript puro. React y Mantine dibujan el mapa y los controles. En la simulación, la criptografía es una marca de confianza puesta en quien firma, y los temporizadores del protocolo están comprimidos para que un corte de luz y un cambio de modo aparezcan en menos de un minuto. La demo va del comportamiento de la malla: quién puede seguir oyendo a quién cuando caen las celdas y los routers sin batería se apagan.

## El mismo plan, dos parejas de modelos

Además de construir, hicimos una pequeña comparación.

Escribimos el plan de ejecución con **Claude Fable 5.1** en Ultramode y luego ejecutamos ese mismo plan dos veces. Una pasada usó **Fable 5.1** con agentes **Opus**. La otra usó **Sonnet 5.5** con agentes **Haiku**.

Lo interesante fue cuánta calidad había ya en el plan. Las dos pasadas terminaron con un producto que funcionaba. La versión de Fable y Opus fue la más pulida, y salió con más funciones. La versión de Sonnet y Haiku se veía sólida y hacía lo que tenía que hacer. La distancia entre las dos fue menor de lo que esperaba. Como pareja más económica, Sonnet y Haiku aguantaban la comparación, porque ejecutaban un plan que Fable ya había dejado muy concreto. La pareja más fuerte recibió las mismas instrucciones y llevó el resultado de sólido a excepcional.

## El estadio, y Kraków

![La pista del HackYeah en el TAURON Arena Kraków](/images/hackyeah-2026-arena.jpg)

Era mi primer hackathon en un sitio así. El pabellón, la luz y la densidad de equipos hicieron que las 24 horas parecieran un festival que, por casualidad, iba de software.

![El HackYeah bajo las luces del estadio](/images/hackyeah-2026-arena-lights.jpg)

El sector informático polaco me dejó una impresión fuerte. Está muy avanzado y muy vivo. Tuve tiempo de hablar con gente más allá de nuestra mesa, y esas conversaciones fueron, de verdad, parte del fin de semana.

![Fuera del TAURON Arena Kraków](/images/hackyeah-2026-tauron-arena.jpg)

Kraków estuvo a la altura del evento. Es una ciudad hermosa, y la comida era excelente.

Un detalle de la sala se me va a quedar grabado. Los organizadores repartieron un chupito energético, Strzał Energii: **200 mg de cafeína en 120 ml**. Es mucha cafeína en una botella muy pequeña.

![El chupito energético de 120 ml del hackathon](/images/hackyeah-2026-energy-shot.jpg)

No llegamos a la final. Aun así, estoy orgulloso del equipo y de lo que hicimos. Tom y Dani fueron unos compañeros estupendos. Trabajamos la idea con verdadera pasión, apretamos el diseño hasta que aguantó, y nos fuimos con una demo que me gusta enseñar.

Estar en la sala del mayor hackathon presencial de Europa es una experiencia que no se me va a olvidar.

[Probar la simulación](https://pomoc.varghacsongor.hu/) · [Ver el vídeo](https://youtu.be/VvQO707MbZQ)
