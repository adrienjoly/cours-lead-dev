# Lead Dev RPG

Le but de chaque équipe est d'obtenir un produit ayant le plus de **valeur** possible, tout en gardant un niveau de **motivation** le plus haut possible, au bout de 4 **sprints** de développement de ce produit.

Chaque équipe est constituée de 4 développeurs, dont 1 lead dev.

En début de partie, le produit de chaque équipe a:
- une **valeur** de `2 points` (nombre entier, intervalle: `]-∞;+∞[`)
- un niveau de **dette technique** de `2 points` (nombre entier, intervalle: `[0;+∞[`)

... et chaque développeur commence avec:
- un niveau de **motivation** de `100%` (nombre entier, intervalle: `[0%;100%]`)
- un niveau de **maitrise** de `10%` (nombre entier, intervalle: `[0%;100%]`)

Un sprint consiste en 5 jours de développement par développeur. Sachant que le lead dev est aussi responsable de la coordination de l'équipe et du suivi des points: il ne dispose que de 3 jours de développement par sprint.

Chaque jour travaillé, chaque développeur peut choisir d'effectuer une **activité** parmi celles de cette liste:
- **Développement** de fonctionnalité => `valeur += 1`, `dette += 1`, `motivation += 5%`, `maitrise += 5%`, `maitrise de chaque autre équipier -= 1%`
- **Documentation** => `dette -= 1`, `motivation -= 5%`, `maitrise de chaque équipier += 2%`
- **Correctif** => `dette -= 1`, `maitrise += 5%`

À chaque fin de sprint, le lead dev de chaque équipe mène une retrospective avec son équipe, en vue d'améliorer ses résultats lors du sprint suivant, et applique les règles suivantes:
- `valeur -= 2` (causé par la concurrence et le vieillissement du produit)
- pour chaque équipier: `motivation += maitrise * valeur > 10 ? 1 : -1` %
- si `dette > 20`, chaque développeur perd 1 journée de travail

Tout au long du sprint, le tableau suivant doit être rempli par chaque équipe:

Sprint nº`XX`  | Lead dev        | Développeur 2   | Développeur 3   | Développeur 4   
---------------|-----------------|-----------------|-----------------|-----------------
Lundi          | `activité=>pts` | `activité=>pts` | `activité=>pts` | `activité=>pts` 
Mardi          | XXXXXXXXXXXXXXX | `activité=>pts` | `activité=>pts` | `activité=>pts` 
Mercredi       | `activité=>pts` | `activité=>pts` | `activité=>pts` | `activité=>pts` 
Jeudi          | XXXXXXXXXXXXXXX | `activité=>pts` | `activité=>pts` | `activité=>pts` 
Vendredi       | `activité=>pts` | `activité=>pts` | `activité=>pts` | `activité=>pts` 
Rétrospective  | => total: `pts` | => total: `pts` | => total: `pts` | => total: `pts`
Rétro. produit | => total valeur: `pts`<br/>=> total dette: `pts` | | |

Occasionellement, le maître du jeu infligera une "tuile" (évènement non prévu) à chaque équipe, parmi cette liste:
- **Bug en production**: `valeur -= arrondi(dette / 10)`
- **Turn-over**: le développeur ayant le plus de maitrise reprend son niveau d'origine (c.a.d. retour à `10%` de maitrise)
- **Requête RGPD**: Chaque développeur qui a une maitrise de moins de `20%` perd une journée de travail pendant ce sprint.
- **Indécision**: Si le lead a moins de `50%` de maitrise, chaque développeur (y compris lui-même) perd une journée de travail pendant ce sprint.
- **Burn out**: le développeur le moins motivé perd deux jours de travail pendant ce sprint et repart à un niveau de maitrise de `10%`.
