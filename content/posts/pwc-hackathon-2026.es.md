+++
draft = false
date = 2026-04-16T00:00:00+02:00
title = "PwC Hackathon 2026: Org Pondus y diseño organizacional con IA"
summary = "Mi equipo y yo participamos en el PwC Hackathon 2026 con Org Pondus: un concepto basado en agentes de IA y grafos ponderados para hiring, workforce planning, retención y estrategia organizacional basada en datos."
tags = ["hackathon", "pwc", "ia", "agents", "aws", "bedrock", "agentcore", "knowledge-graph", "hr-tech"]
categories = ["hackathons"]
+++

## PwC Hackathon 2026
**16 de abril de 2026**  
**PwC Hungría, Budapest**  
Preselección • pitch de concepto de negocio • MVP canvas • planificación de ROI • plan de ejecución del hackathon

Mi equipo y yo participamos en el **PwC Hackathon 2026**, un hackathon de alto nivel y con una estructura poco habitual en Budapest. Trabajé junto con **Erdős Péter Zsombor** y **Vargha Bendegúz Attila**, mi hermano, bajo el nombre de equipo **The Professionals**.

El evento fue diferente a la mayoría de hackathons en los que he participado. Antes de llegar a la fase final de construcción, los equipos tenían que pasar una preselección y preparar un paquete de pitch serio: un **concepto de negocio de 6-8 diapositivas**, un **MVP canvas**, un **modelo de ROI** y un **plan realista de ejecución para el hackathon**. No conseguimos entrar entre los 15 equipos finalistas, pero aun así considero que la experiencia fue muy valiosa. Creamos una propuesta significativa, la refinamos bajo presión e hicimos excelentes conexiones profesionales.

![El equipo The Professionals en el PwC Hackathon 2026](/images/pwc-hackathon-2026-team.png)

Uno de los momentos más importantes para mí fue poder hablar con el liderazgo de PwC Hungría y tener conversaciones técnicas con los responsables de Cloud Engineering y AI Engineering. Eso hizo que el evento fuera mucho más que una competición: también fue una oportunidad poco común para validar una idea con personas que entienden tanto la tecnología enterprise como la transformación de negocio.

## Nuestra propuesta: Org Pondus
Nuestro concepto se llamó **Org Pondus**: una plataforma basada en agentes de IA y grafos ponderados para desarrollar y proteger organizaciones.

El problema principal que queríamos abordar es que muchas organizaciones todavía toman decisiones de hiring, planificación de personal y capacidades internas sin un mapa claro y basado en datos de su propia estructura. Con demasiada frecuencia, estas decisiones se basan en intuición, información fragmentada o impresiones subjetivas de management. En grandes empresas, esto puede llevar a contratar a la persona equivocada para el rol equivocado, ocultar brechas de capacidades, sobrecargar equipos clave, desaprovechar departamentos y ralentizar el crecimiento orgánico.

**Org Pondus** fue diseñado para crear una visión más objetiva y continuamente actualizada de una organización, combinando:
- Bases de conocimiento existentes y documentación interna
- Eventos de sistemas de HR y ticketing
- Datos públicos y de mercado cuando sean relevantes
- Un grafo organizacional ponderado
- Agentes de IA especializados para hiring, workforce planning y evaluación estratégica

El objetivo no era reemplazar el juicio de liderazgo. Era dar a líderes, equipos de HR y managers una base factual más fuerte: dónde falta capacidad, qué equipos están sobrecargados, qué capacidades son estratégicamente importantes y cuándo conviene contratar, reequilibrar o invertir en retención.

## Dirección técnica
La propuesta técnica era una arquitectura basada en agentes en la nube, con AWS como implementación de referencia.

![Sistema de agentes de Org Pondus](/images/pwc-hackathon-2026-agent-system.png)

En el centro del diseño estaba **Amazon Bedrock AgentCore Runtime**, coordinando varios agentes especializados:
- **Hiring Manager Agent** para definición de roles y recomendaciones de contratación
- **Organization Tree Balancing Agent** para análisis de capacidad y estructura
- **Organization Strategy Evaluator Agent** para evaluar trade-offs estratégicos
- **Workforce Decisionmaker Agents** para soporte a decisiones operativas

Estos agentes se conectarían mediante **AgentCore Gateways** a sistemas empresariales y fuentes de conocimiento como herramientas de ticketing, LinkedIn, Hays, bases de conocimiento internas y datos organizacionales. Una **Bedrock Knowledge Base** y una capa de grafo con **Amazon Neptune** proporcionarían tanto conocimiento semántico como relaciones organizacionales estructuradas.

![Arquitectura de alto nivel de Org Pondus](/images/pwc-hackathon-2026-high-level-architecture.png)

La arquitectura propuesta incluía:
- **Route 53, CloudFront, S3, API Gateway, WAF y Lambda** para una capa web y API serverless
- **EventBridge** para procesar eventos de HR y ticketing casi en tiempo real
- **Modelos de IA en Bedrock** para razonamiento, generación de recomendaciones e interacción en lenguaje natural
- **Bedrock AgentCore Runtime** para orquestar el sistema de agentes
- **Bedrock Knowledge Base** para recuperación de conocimiento específico de la empresa
- **Amazon Neptune** para el grafo organizacional ponderado
- **Integraciones tipo MCP** con Jira, Hays, LinkedIn y sistemas internos

También planeamos un frontend para visualizar el grafo organizacional, resaltar fortalezas y debilidades críticas, y configurar prioridades estratégicas para alinear las recomendaciones con los objetivos de la empresa.

## Valor de negocio y ROI
El caso de negocio se centró en mejoras medibles en hiring, retención y planificación organizacional.

Propusimos un modelo SaaS con pricing basado también en uso, empezando por empresas tecnológicas con muchos datos y escalando después hacia pymes y clientes enterprise. La presentación estimaba una inversión inicial de unos **15.000 EUR** para una primera iteración usable en producción, seguida de costes mensuales de infraestructura, uso de modelos, soporte y ventas.

El valor esperado para los clientes incluía:
- Procesos de hiring más rápidos y baratos
- Menor rotación gracias a detección temprana de riesgos
- Distribución de carga de trabajo más equilibrada
- Planificación de capacidad más objetiva
- Mejor visibilidad sobre fortalezas y debilidades organizacionales
- Reporting, predicción y soporte de decisiones continuo basado en datos reales

La idea era ambiciosa, pero intencionalmente práctica: empezar con un MVP, validarlo con empresas abiertas a alpha testing y profundizar las integraciones a medida que el modelo organizacional ganara utilidad.

## Lo que me llevé
Aunque no avanzamos a los 15 finalistas, estoy orgulloso del concepto. El formato nos obligó a pensar más allá de una demo y considerar factibilidad, ROI, planificación de implementación y adopción enterprise desde el principio.

Gracias a **PwC** por organizar el evento y crear un espacio donde el pensamiento técnico y de negocio pudieron encontrarse. También agradezco a **Erdős Péter Zsombor** y **Vargha Bendegúz Attila** por el trabajo en equipo, la energía y las conversaciones honestas que dieron forma a la propuesta.

Fue un buen recordatorio de que un hackathon puede ser exitoso incluso sin llegar a la final, si produce una mejor idea, pensamiento más claro y relaciones profesionales significativas.
