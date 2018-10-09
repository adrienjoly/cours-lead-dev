# Tuiles

Occasionnellement, le maître du jeu infligera une "tuile" (évènement non prévu) aux équipes, parmi cette liste:

- **Bug en production**: Une des fonctionnalités livrée ne fonctionne plus => il faut la réparer en priorité !

- **Turn-over**: Deux développeurs changent d'équipe => il va falloir s'adapter

- **Requête RGPD**: Un utilisateur demande une feuille expliquant quelles données le concernant sont stockées par le produit, comment/où elles sont stockées (sans oublier d'inclure les prestataires), pour quelles raison, et sous quelle forme/format ces données pourraient lui être fournies. => un des développeurs va devoir rédiger cette feuille de manière la plus réaliste et complète possible.

- **Faille de sécurité dans une dépendance**

- **Passage à webpack 4**: La mise à jour de cette dépendance présente des *breaking changes* => il va falloir redessiner une des fonctionnalités, en utilisant une règle, cette fois.

- **Internationalisation**: Votre entreprise vient de signer un beau client Anglophone => il va falloir redessiner une des fonctionnalités en langue Anglaise.

- **La CI est cassée**: vous avez le choix entre bloquer geler l'intégration des nouvelles fonctionnalités (=> plus aucune fonctionnalité comptabilisés comme "terminées" avant le prochain sprint, à partir de maintenant), ou quand même les intégrer et découvrir un bug en production lors du prochain sprint (=> une de vos fonctionnalité sera cassée et devra être corrigée lors du prochain sprint).

<!-- tuiles difficilement traduisible dans le jeu:
- **Influence extérieure**: le CEO influence les devs => ils ne suivent plus la roadmap prévue => perte de velocité
-->
