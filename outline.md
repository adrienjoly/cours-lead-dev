# Cours Lead Dev

## TODO

- [x] Points à couvrir => outline
- [x] QCM individuel en fin de 1ère journée
- [x] Comment va se passer chaque atelier ? (règles du jeu)
- [ ] Contrôle continu: comment noter individuellement les étudiants, sur la base de leur travail en ateliers ?

## Outline

- Jour 1, Objectif: sensibilisation aux responsabilités et complexités du lead dev
  - QCM à main levée: cassage de mythes sur le lead dev
    - lead dev = meilleur développeur de l'équipe ? -> NON
    - lead dev passe la majorité de son temps à développer ? -> OUI
    - lead dev est élu par ses supérieurs hiérarchiques ? -> NON
    - lead dev tranche quand il y a un conflit au sein de l'équipe sur une décision technique ? -> OUI
    - lead dev décide de qui fait quoi, quand, dans l'équipe ? -> NON
    - lead dev doit détécter et planifier le remboursement de la dette technique ? -> OUI
    - lead dev décide l'ordre de développement des fonctionnalités ? (roadmap) -> NON
    - lead dev est responsable du recrutement ? -> NON
    - lead dev est responsable du développement de carrière des ingénieurs de son équipe ? -> NON
    - lead dev doit régulièrement parler aux clients ? -> NON
  - Rappels sur les métiers, rôles et méthodologies de projet en entreprise
    - métiers / rôles:
      - lead dev:
        - son role: aider et coordonner l'équipe de développement
        - son objectif: la pérennité technique du projet,
        - il doit être force d'initiative
        - il doit être en mesure de trancher sur les décisions techniques
        - rapporteur, (prise de notes, rédaction de comptes rendus de réunions et incidents)
        - référent d'une équipe de développement, il discute majoritairement avec son équipe, mais aussi avec autres équipes techniques + managers
        - le lead dev peut agir comme project manager, si besoin
      - project manager / scrum master:
        - son role: planifier, suivre et faciliter le bon déroullement d'un projet
        - son objectif: l'équipe produit un résultat répondant aux attentes, en respectant au mieux les budgets (temps, argent) et les éventuelles interdépendances avec autres projets, et les imprévus
      - product manager / product owner:
        - son role: identifier les besoins des clients du produit, aider l'équipe de développement à prioriser les évolutions en fonction
        - son objectif: une clientèle durablement satisfaite, et croissante + permettre à l'équipe de développement d'avoir un maximum d'impact et d'efficacité en focalisant sur ce qui apporte le plus de valeur
      - engineering manager:
        - son role: suivre, conseiller et aider les développeurs à s'améliorer de manière continue, et à développer leur carrière. + recruter.
        - son objectif: maintenir ou faire croitre la force et la qualité des développements
    - méthodos
      - Cycle en V
      - Gestion projet: Gantt, etc...
      - Agile / Scrum
      - Lean management / lean startup
      - Extreme Programming
      - UML
      - Git / GitHub / GitLab flow
- Jour 2, Objectif: bases et outils pour la gestion de crise
  - Brainstorming: lister des exemples de crises qui peuvent survenir lors d’un projet
    - problèmes techniques / incidents / urgences
      - lenteur de l'infra
      - page 503 (site inaccessible)
      - problème de facturation (ex: causé par un problème de monitoring)
      - fuite de données
      - alteration de données
      - perte de données
    - problèmes de qualité / architecture du produit
      - régressions
      - bugs
      - manque de prévisibilité du comportement du produit
      - difficulté de faire contribuer des personnes extérieures à l'équipe
    - manque d'équilibre / d'efficacité
      - trop de temps passé sur bug fixes, pas assez de nouvelles fonctionnalités
      - trop de temps passé sur nouvelles fonctionnalités, pas assez sur bug fixes
      - trop de temps passé en support client (bugs, questions...)
      - trop de temps passé à répondre aux questions des autres équipiers
      - trop de temps passé à lire les pull requests
      - trop d'itérations sur les pull requests (ex: discussions, documentation, linting...)
      - over-engineering
      - les nouvelles fonctionnalités prennent beaucoup plus de temps qu'elles ne devraient à développer
    - problèmes humains
      - conflit intra-équipe sur une décision technique (ex: architecture d'une solution à produire)
      - l'équipe ne respecte pas la roadmap / le backlog
      - baisse de motivation et productivité de l'équipe
      - pas assez de monde en astreinte / équipier en astreinte qui ne répond jamais aux urgences
    - demandes GDPR
- Jour 3, Objectif: recommandations pour pérennité, prise d’initiatives et accompagnement des membres de l’équipe
  - Brainstorming: quelles responsabilités du lead dev, au delà des crises ?
    - choix technologiques => veille et compréhension des valeurs et direction de l'entreprise
    - élaboration des budgets:
      - développement de fonctionnalités,
      - support,
      - correction de bugs,
      - détection et remboursement de dette technique,
      - documentation,
      - tests automatisés,
      - monitoring et alertes,
      - mise en place et suivi d'astreintes (post-mortem, etc...)
      - entraide et communication externe (ex: pour recrutement)
      - animation de l'équipe: hack day, off-site, et autres activités de team building

## Atelier - Règles du jeu

Le but de chaque équipe est d'obtenir un produit ayant le plus de **valeur** possible, tout en gardant un niveau de **motivation** le plus haut possible, au bout de 4 **sprints** de développement de ce produit.

Chaque équipe est constituée de 4 développeurs, dont 1 lead dev.

En début de partie, le produit de chaque équipe a:
- une **valeur** de `2 points` (nombre entier, intervalle: `]-∞;+∞[`)
- un niveau de **dette technique** de `2 points` (nombre entier, intervalle: `[0;+∞[`)

... et chaque développeur commence avec:
- un niveau de **motivation** de `100%` (nombre entier, intervalle: `[0%;100%]`)
- un niveau de **maitrise** de `10%` (nombre entier, intervalle: `[0%;100%]`)

Un sprint consiste en 5 jours de développement par développeur. Sachant que le lead dev est aussi responsable de la coordination de l'équipe et du suivi des points: il ne dispose que de 3 jours de développement par sprint.

Chaque jour travaillé, chaque développeur peut choisir d'effectuer une activité parmi celles de cette liste:
- **Développement** de fonctionnalité => `valeur += 1`, `dette += 1`, `motivation += 5%`, `maitrise += 5%`, `maitrise de chaque autre équipier -= 1%`
- **Documentation** => `dette -= 1`, `motivation -= 5%`, `maitrise de chaque équipier += 2%`
- **Correctif** => `dette -= 1`, `maitrise += 5%`

À chaque fin de sprint, le lead dev de chaque équipe mène une retrospective avec son équipe, en vue d'améliorer ses résultats lors du sprint suivant, et applique les règles suivantes:
- `valeur -= 2` (causé par la concurrence et le vieillissement du produit)
- pour chaque équipier: `motivation += maitrise * valeur > 10 ? 1 : -1` %
- si `dette > 20`, chaque développeur perd 1 journée de travail

Tout au long du sprint, le tableau suivant doit être rempli par chaque équipe:

Sprint nº`XX`  | Lead dev      | Développeur 2 | Développeur 3 | Développeur 4
---------------|---------------|---------------|---------------|---------------
Lundi          | `activité`    | `activité`    | `activité`    | `activité`    
               | `=> points`   | `=> points`   | `=> points`   | `=> points`   
---------------|---------------|---------------|---------------|---------------
Mardi          | XXXXXXXXXXXXX | `activité`    | `activité`    | `activité`    
               | XXXXXXXXXXXXX | `=> points`   | `=> points`   | `=> points`   
---------------|---------------|---------------|---------------|---------------
Mercredi       | `activité`    | `activité`    | `activité`    | `activité`    
               | `=> points`   | `=> points`   | `=> points`   | `=> points`   
---------------|---------------|---------------|---------------|---------------
Jeudi          | XXXXXXXXXXXXX | `activité`    | `activité`    | `activité`    
               | XXXXXXXXXXXXX | `=> points`   | `=> points`   | `=> points`   
---------------|---------------|---------------|---------------|---------------
Vendredi       | `activité`    | `activité`    | `activité`    | `activité`    
               | `=> points`   | `=> points`   | `=> points`   | `=> points`   
---------------|---------------|---------------|---------------|---------------
Rétrospective  | motivation: % | motivation: % | motivation: % | motivation: %
               | maitrise:   % | maitrise:   % | maitrise:   % | maitrise:   % 
---------------|---------------|---------------|---------------|---------------
Rétro. produit | valeur: (pts)
               | dette:  (pts)

Occasionellement, le maître du jeu infligera une "tuile" (évènement non prévu) à chaque équipe, parmi cette liste:
- **Bug en production**: `valeur -= arrondi(dette / 10)`
- **Turn-over**: le développeur ayant le plus de maitrise reprend son niveau d'origine (c.a.d. retour à `10%` de maitrise)
- **Requête RGPD**: Chaque développeur qui a une maitrise de moins de `20%` perd une journée de travail pendant ce sprint.
- **Indécision**: Si le lead a moins de `50%` de maitrise, chaque développeur (y compris lui-même) perd une journée de travail pendant ce sprint.
- **Burn out**: le développeur le moins motivé perd deux jours de travail pendant ce sprint et repart à un niveau de maitrise de `10%`.
