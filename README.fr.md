[English](README.md) · **Français**

**Anthony Hunt** · [Fiche du projet sur ingevision.cloud](https://ingevision.cloud/agents-ia/?p=agent-equipe-de-nuit) · [LinkedIn](https://www.linkedin.com/in/anthony-hunt-3948a9196) · [Profil GitHub](https://github.com/anthohunt)

> Dépôt vitrine : le code et les données de ce projet sont privés ; ce README le décrit.

# Agent - Équipe de nuit du site

Cinq agents qui s'occupent d'un site personnel chaque nuit, l'un après l'autre : qualité, performance, sécurité, et deux qui cherchent les personnes à qui il peut servir. Le matin, un mail court résume ce qu'ils ont corrigé et ce qui reste à décider.

## Le problème

Un site tenu par une seule personne dérive sans bruit : un lien casse, une fiche ne correspond plus à son dépôt, une page s'alourdit, un en-tête de sécurité manque, la version anglaise prend du retard. Tout vérifier à la main chaque semaine est le genre de corvée qui ne se fait jamais.

## Comment ça marche

- **Un agent par créneau de nuit**, sur une machine à la maison : clients à minuit, recrutement à 1 h, qualité à 2 h, performance à 3 h, sécurité à 4 h. Chacun a sa mission écrite et sa mémoire des nuits passées.
- **Qualité** rejoue chaque user story de la maquette du site dans un vrai navigateur, sur ordinateur et sur téléphone, ouvre chaque fiche dans les deux langues et la compare à son dépôt GitHub.
- **Performance** mesure le poids et la vitesse des pages et garde les chiffres nuit après nuit : un chiffre qui se dégrade est une faute, même s'il reste « correct ».
- **Sécurité** contrôle les en-têtes, les certificats, les bibliothèques, et qu'aucune donnée personnelle ne fuit dans les pages ou les dépôts publics.
- **Clients et recrutement** préparent seulement : qui pourrait être intéressé, ce qu'on pourrait publier. Ils ne contactent personne.
- **Ce qu'un agent fait seul** : les corrections factuelles et mécaniques (lien cassé, « En ligne : Non » faux, en-tête manquant). Il met en ligne, vérifie le résultat en ligne sur ordinateur et téléphone, puis commite avec la raison. Une correction qu'il ne voit pas marcher en ligne est défaite.
- **Ce qu'il propose seulement** : un texte, le design, tout ce qui est un choix du propriétaire. Le mail du matin les liste avec un identifiant ; répondre « oui ID » ou « non ID » suffit.
- **L'effort est compté, pas déclaré** : un script relit la session de chaque agent (actions faites, pages ouvertes, user stories citées, dépôts vérifiés). Sous le plancher, l'agent est relancé sur ce qui manque.

## Ce qui est construit

En service depuis le 9 novembre 2026. Première nuit : 142 vues de pages contrôlées sans erreur JavaScript, 46 user stories conformes sur 47 après une correction, 30 fiches vérifiées dans les deux langues, 3 corrections mises en ligne (retour arrière au téléphone, plan du site, un champ « En ligne » faux) ; HTTPS imposé et politique de sécurité du contenu ajoutée ; polices servies par le site lui-même au lieu d'un tiers.

## Ce qui est public

Cette page seulement. Les missions, mémoires et rapports décrivent une installation privée.

## Technologies

- Agents Claude Code, lancés sans écran selon un horaire
- Playwright (vrai navigateur, ordinateur et téléphone)
- Python (compteur d'effort, mail du matin, lecture des réponses)
- nginx, git
