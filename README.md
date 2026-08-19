<h1 align="center">Manuel González Rivera</h1>

<p align="center">
  <b>Senior Software Engineer</b><br>
  Houston, TX · Open to conversations about interesting problems
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/manuelgonzalezr">LinkedIn</a> ·
  <a href="https://fieldseal.dev">fieldseal.dev</a>
</p>

---

Twenty-plus years in systems analysis, solutions architecture, and integration work —
fintech, SaaS, health, education. Most of what I do well sits in the unglamorous
middle: the migration nobody wants to own, the integration with an API that lies, the
cloud bill that turns out to be an architecture diagram.

Currently focused on AI-assisted delivery and agent orchestration — designing the
workflows and reusable skills that remove recurring development work instead of doing
it by hand every time.

## Building now — Fieldseal

An open specification for **transparent field-level encryption-at-rest**, applied at
the data-access layer so applications stop hand-rolling crypto per column.

The genuinely hard part is search. Once a field is encrypted you can no longer index
it, so you add a blind index — a keyed hash you *can* look up. Every blind index leaks
something: equality, cardinality, distribution. Most designs mention this in passing.
Fieldseal declares a **leakage budget explicitly**, so the tradeoff you're accepting is
written down and reviewable rather than discovered in an audit two years later.

Around that: a self-describing ciphertext envelope, a frozen cipher-suite registry, a
key hierarchy, a threat model, 15+ design decision records, machine-readable
interoperability test vectors, and operational guidance for key rotation and
zero-downtime migration.

Core libraries target **Python, TypeScript, Java, .NET, and Go**, with thin ORM
adapters for Django, Prisma, SQLAlchemy, Hibernate, EF Core, GORM, and TypeORM.

→ [fieldseal.dev](https://fieldseal.dev) · [github.com/fieldseal-dev](https://github.com/fieldseal-dev)

## Problems I've spent time on

**A GraphQL API spread across Lambdas.** Every resolver was its own function, so a
single query fanned out into a burst of cold starts and a long conversation the system
was having with itself. Consolidating onto one ECS service cut response times by 93%
and removed 70% of the traffic, nearly all of it internal. What I kept from it:
distribution is a cost you pay per boundary, and resolvers are the wrong place to draw
one.

**Moving 250,000 users without losing anyone.** The hard part of a migration isn't the
move, it's proving the move was correct. I helped design the tooling that carried 300M+
records onto new infrastructure and then reconciled them, so "it worked" was something
we could check per record instead of assert. Migrations fail quietly; reconciliation is
what makes the failure loud.

**The last 7% of reliability lives in other people's APIs.** Content publishing across
9 social networks sat at 92%. Getting past 99% wasn't one fix — it was treating each
network's failure modes as a first-class domain concern rather than a transport error:
rate-limit semantics, silent truncation, tokens expiring mid-queue. Reliability against
systems you don't control is a modeling problem, not a retry problem.

**A 43% cloud bill reduction that was really an architecture review.** I went looking
for waste in an AWS bill and mostly found architecture — services provisioned for a
peak that had moved, data crossing boundaries it had no reason to cross, retention
policies nobody had revisited. Cost is a lagging indicator of design decisions, which
makes the invoice an unusually honest diagram of the system.

## Tech

**Languages**

![PHP](https://img.shields.io/badge/PHP-777BB4?style=flat-square&logo=php&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)

**Frameworks & APIs**

![Laravel](https://img.shields.io/badge/Laravel-FF2D20?style=flat-square&logo=laravel&logoColor=white)
![Symfony](https://img.shields.io/badge/Symfony-000000?style=flat-square&logo=symfony&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-5FA04E?style=flat-square&logo=nodedotjs&logoColor=white)
![Next.js](https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white)
![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black)
![GraphQL](https://img.shields.io/badge/GraphQL-E10098?style=flat-square&logo=graphql&logoColor=white)

**Cloud & Data**

![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![MongoDB](https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-FF4438?style=flat-square&logo=redis&logoColor=white)

Also: systems analysis and requirements definition, threat modeling, data migration and
reconciliation, CI/CD pipelines, Agile/Scrum, PHPUnit · Behat · Jest.

## Elsewhere

The full timeline — employers, roles, and everything back to 2003 — lives on
[LinkedIn](https://www.linkedin.com/in/manuelgonzalezr).

Off-hours I write automation scripts for Bitburner, a hacking game, which is either a
break from the day job or exactly the same thing.

---

<details>
<summary><b>🇪🇸 Español</b></summary>

Más de veinte años en análisis de sistemas, arquitectura de soluciones e integración —
fintech, SaaS, salud y educación. Lo que mejor hago vive en la parte menos vistosa: la
migración que nadie quiere asumir, la integración con una API que miente, la factura de
nube que resulta ser un diagrama de arquitectura.

Actualmente enfocado en desarrollo asistido por IA y orquestación de agentes — diseñando
los flujos de trabajo y las habilidades reutilizables que eliminan el trabajo recurrente
en lugar de repetirlo a mano cada vez.

## Construyendo ahora — Fieldseal

Una especificación abierta para el **cifrado transparente a nivel de campo en reposo**,
aplicado en la capa de acceso a datos para que las aplicaciones dejen de improvisar
criptografía columna por columna.

La parte verdaderamente difícil es la búsqueda. Una vez cifrado un campo ya no se puede
indexar, así que se añade un índice ciego: un hash con llave que *sí* se puede consultar.
Todo índice ciego filtra algo — igualdad, cardinalidad, distribución. La mayoría de los
diseños lo mencionan de pasada. Fieldseal **declara un presupuesto de fuga explícito**,
de modo que el compromiso que aceptas queda escrito y es revisable, en vez de descubrirse
en una auditoría dos años después.

Alrededor de eso: un sobre de texto cifrado autodescriptivo, un registro cerrado de
suites criptográficas, una jerarquía de llaves, un modelo de amenazas, más de 15 registros
de decisiones de diseño, vectores de prueba de interoperabilidad legibles por máquina y
guía operativa para rotación de llaves y migración sin tiempo de inactividad.

Las bibliotecas principales apuntan a **Python, TypeScript, Java, .NET y Go**, con
adaptadores ligeros para Django, Prisma, SQLAlchemy, Hibernate, EF Core, GORM y TypeORM.

→ [fieldseal.dev](https://fieldseal.dev) · [github.com/fieldseal-dev](https://github.com/fieldseal-dev)

## Problemas en los que he trabajado

**Una API GraphQL repartida en Lambdas.** Cada resolver era su propia función, así que
una sola consulta se abría en una ráfaga de arranques en frío y en una larga conversación
que el sistema mantenía consigo mismo. Consolidar todo en un único servicio sobre ECS
redujo los tiempos de respuesta un 93% y eliminó el 70% del tráfico, casi todo interno.
Lo que me quedó: la distribución es un costo que se paga por frontera, y los resolvers
son el lugar equivocado para trazar una.

**Mover 250,000 usuarios sin perder a nadie.** Lo difícil de una migración no es el
traslado, sino demostrar que fue correcto. Ayudé a diseñar las herramientas que llevaron
más de 300 millones de registros a una nueva infraestructura y luego los reconciliaron,
para que "funcionó" fuera algo verificable registro por registro y no una afirmación. Las
migraciones fallan en silencio; la reconciliación es lo que hace ruidoso el fallo.

**El último 7% de confiabilidad vive en las APIs de otros.** La publicación de contenido
en 9 redes sociales estaba en 92%. Superar el 99% no fue un solo arreglo — fue tratar los
modos de fallo de cada red como parte del dominio y no como un error de transporte:
semántica de límites de tasa, truncamiento silencioso, tokens que expiran a medio proceso.
La confiabilidad frente a sistemas que no controlas es un problema de modelado, no de
reintentos.

**Una reducción del 43% en la factura de nube que en realidad fue una revisión de
arquitectura.** Fui a buscar desperdicio en una factura de AWS y encontré sobre todo
arquitectura: servicios aprovisionados para un pico que ya se había movido, datos cruzando
fronteras sin razón, políticas de retención que nadie había revisado. El costo es un
indicador rezagado de las decisiones de diseño, lo que convierte a la factura en un
diagrama inusualmente honesto del sistema.

## En otros lugares

La trayectoria completa — empleadores, puestos y todo lo anterior desde 2003 — está en
[LinkedIn](https://www.linkedin.com/in/manuelgonzalezr).

Fuera del horario escribo scripts de automatización para Bitburner, un juego de hacking,
lo cual es un descanso del trabajo diario o exactamente lo mismo.

</details>
