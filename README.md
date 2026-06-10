# REL - Projet 1

# Partager une ressource éducative libre
> **Outil d'aide à la décision** 
Une application web qui accompagne le personnel enseignant pour partager une ressource éducative libre (REL). Elle répond en un seul parcours guidé à deux questions : *est-il pertinent de partager cette ressource ?*, puis *quelle licence Creative Commons lui convient ?*
---
## Présentation
Beaucoup de personnes enseignantes hésitent à diffuser leurs ressources : par crainte des aspects légaux, par incertitude sur la qualité « suffisante », ou parce que le choix d'une licence paraît opaque. Cet outil lève ces freins en deux étapes. Il aide d'abord à décider **s'il est pertinent de partager**, en distinguant ce qui relève d'un simple curseur de qualité de ce qui constitue un garde-fou légal. Il guide ensuite vers la **bonne licence Creative Commons**, en privilégiant l'ouverture (CC BY, par défaut au SSF) et en signalant les conditions restrictives comme des exceptions à justifier. Tout se déroule dans le navigateur : **aucune donnée n'est envoyée ni conservée.**

## Ce que fait l'outil
**Étape 1 - Est-ce pertinent de partager ?**
- Un volet **Aspects légaux obligatoires** (propriété intellectuelle, compatibilité des licences, éthique, consentements), évalués en *Oui / À valider / Non* - un seul « non » suspend le partage.
- Trois volets à cocher : **Potentiel de réutilisation**, **Qualité**, **Rayonnement**.
- Un **feu de circulation en direct** synthétise la décision : rouge (blocage légal), jaune (à compléter ou qualité à renforcer), vert (prêt à partager).

**Étape 2 - Quelle licence choisir ?**
- Quatre questions (droits détenus, adaptation, partage à l'identique, usage commercial) qui mènent à la licence appropriée.
- Des rappels pédagogiques signalent les conditions **ND** et **NC** comme des exceptions.
- Un **générateur de mention** produit l'attribution (format Standard ou APA) avec le lien vers la licence et le badge CC, copiable en un clic - logo compris.

## Fonctionnalités

- Verrou logique : l'étape 2 ne se déverrouille qu'une fois les aspects légaux réglés.
- Jauge de progression des aspects légaux (« X / 4 prêts »).
- Suivi d'étape persistant dans l'en-tête fixe.
- Barre de statut fixe sur mobile pour garder le feu de circulation visible.
- Copie de la mention avec **logo intégré** (image embarquée, qui se colle dans Word, Google Docs et les courriels).
- Accessibilité : navigation clavier, focus visibles, statut annoncé (`aria-live`), respect de `prefers-reduced-motion`.

## Déploiement (GitHub Pages, sans compilation)
Le fichier `index.html` est autonome : React et Babel sont chargés par CDN, aucune installation n'est requise.
Instructions pour répliquer ce projet
1. Créer un dépôt **public** sur GitHub.
2. Y téléverser `index.html` à la racine, puis valider (*commit*).
3. Aller dans **Settings → Pages**, choisir **Source : Deploy from a branch**, branche `main`, dossier `/ (root)`.
4. Après une minute, l'outil est en ligne à `https://<votre-nom>.github.io/<nom-du-depot>/`.

> Remarque : Babel compile le code dans le navigateur au chargement (léger délai initial). Pour un usage à fort trafic, une version compilée avec Vite est préférable.

## Personnalisation
- **Garantir la copie du logo.** Pour une fiabilité totale quel que soit le navigateur, hébergez les badges PNG dans le dépôt (p. ex. un dossier `badges/`) et remplacez le helper `badgeUrl` par un chemin local (`/badges/${code}.png`). 
- **Couleurs et textes** se modifient dans le bloc `:root` et les constantes en tête de fichier (`THEMES`, `LEGAL_ITEMS`, `LICENSES`).

## Confidentialité
L'outil fonctionne entièrement côté navigateur. Aucune réponse, aucune saisie n'est transmise à un serveur ni stockée.
## Liens utiles
- Balises éditoriales du SSF : <https://zenodo.org/records/14963025>
- Politique sur la propriété intellectuelle (UdeS) : <https://www.usherbrooke.ca/decouvrir/fileadmin/sites/decouvrir/documents/direction/politiques/2500-049.pdf>
- Assistant officiel Creative Commons : <https://creativecommons.org/chooser/>

## Crédits et licence
Réalisé par Alexandra Lez.
Cet outil est lui-même une ressource éducative libre, diffusée sous licence **Creative Commons Attribution 4.0 International (CC BY 4.0)**. Vous êtes libre de le réutiliser et de l'adapter, à condition d'en créditer la source.

> « Partager une ressource éducative libre - Outil d'aide à la décision »  est mis à disposition selon les termes de la licence [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/deed.fr).
