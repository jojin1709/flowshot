<div align="center">

<img src="public/mascot.svg" width="140" height="140" alt="FlowShot" />

# FlowShot

**Capture automatiquement tout flux de navigateur en un guide étape par étape.**

Cliquez sur enregistrer, faites ce que vous avez à faire, et obtenez un guide professionnel avec des captures d'écran annotées. Commentez en cours de route, éditez après, puis rejouez ou exportez. Sans compte, sans cloud, sans traçabilité.

[![License][license-shield]][license-link]
[![Manifest V3][mv3-shield]][mv3-link]
[![100% Local][local-shield]][local-link]
[![No Account][no-account-shield]][no-account-link]

</div>

---

## Table des Matières

- [Qu'est-ce que FlowShot ?](#quest-ce-que-flowshot)
- [Fonctionnalités](#fonctionnalités)
- [Navigateurs Supportés](#navigateurs-supportés)
- [Démarrage Rapide](#démarrage-rapide)
- [Confidentialité et Stockage](#confidentialité-et-stockage)
- [Contribuer](#contribuer)
- [Licence](#licence)

---

## Qu'est-ce que FlowShot ?

FlowShot est une extension de navigateur qui capture automatiquement vos flux de travail et les transforme en guides étape par étape avec des captures d'écran annotées. Tout fonctionne dans votre navigateur — pas de backend, pas de compte, pas de télémétrie, rien ne quitte votre appareil.

Que vous documentiez des outils internes, rédigiez des tutoriels ou formiez un collègue, FlowShot capture chaque clic, frappe et navigation pour que vous puissiez vous concentrer sur le reste.

Chaque action significative devient une étape : clics sur boutons et liens, champs de formulaire, raccourcis clavier, actions de presse-papiers, glisser-déposer et navigations. Les clics rapides sur des éléments proches sont fusionnés pour que les guides restent propres, et le clic est intercepté avant que la page ne navigue, donc rien n'est perdu sur les SPAs ou les chargements complets.

Chaque étape contient une capture d'écran avec l'élément cliqué mis en évidence et zoomé. Pas de recadrage manuel, pas d'outils d'annotation à apprendre.

---

## Fonctionnalités

### Smart Blur

FlowShot détecte et floute automatiquement les données sensibles dans vos captures : e-mails, numéros de téléphone, numéros de sécurité sociale, cartes bancaires, adresses IP, adresses MAC. Activez ou désactivez chaque catégorie indépendamment.

Besoin de flouter quelque chose de personnalisé ? Le sélecteur manuel vous permet de choisir n'importe quel élément du DOM et de le masquer dans toutes les captures où il apparaît.

### Descriptions IA

Apportez votre propre clé API (OpenAI ou Anthropic) et FlowShot génère des descriptions lisibles comme *« Cliquez sur le bouton **Envoyer** pour sauvegarder »* au lieu de `Click button "Submit"`.

Les descriptions sont générées à partir d'un contexte DOM léger (~50-100 tokens), pas depuis les captures. Environ 15-30 fois moins cher que les modèles avec vision. Choisissez la langue des descriptions (anglais, espagnol, portugais, français).

### Rejouer Guide Me

Rejouez n'importe quel guide en direct sur une vraie page. FlowShot met en évidence l'élément suivant, suit votre progression étape par étape, et avance tout seul au fur et à mesure. Parfait pour former un collègue ou se guider soi-même.

### Narration Vocale

Parlez à voix haute pendant que vous enregistrez et FlowShot transforme ce que vous avez dit en descriptions d'étapes. L'audio est transcrit avec votre propre clé (OpenAI ou Groq) et associé aux étapes correspondantes, donc vous ne narrativez qu'une fois au lieu d'écrire chaque étape à la main.

### Éditeur de Guide

Corrigez un guide après coup sans réenregistrer. Recadrez, annotez et censurez n'importe quelle capture, réécrivez une étape avec l'IA directement, insérez des titres et des notes entre les étapes, réorganisez ou supprimez en lot, et revenez en arrière avec l'historique des versions.

### Export Multi-Formats

Partagez vos guides dans le format qui correspond le mieux à votre flux de travail :

| Format | Détails |
|--------|---------|
| **Vidéo** | Parcours narré, mp4/H.264, avec mouvement du curseur |
| **PDF** | Prêt à imprimer, A4 portrait avec sauts de page automatiques |
| **DOCX** | Ouvrez et continuez à éditer dans Word |
| **HTML** | Autonome, images intégrées en base64 |
| **Markdown** | Collez dans Notion, GitHub, documentation interne, wikis |

Toutes les exportations sont générées côté client. Rien ne passe par un serveur.

---

## Navigateurs Supportés

| Navigateur | Statut |
|------------|--------|
| Google Chrome | Supporté |
| Mozilla Firefox | Supporté |
| Microsoft Edge | Supporté |
| Brave | Supporté |

Disponible en anglais, espagnol, portugais brésilien, français et allemand. La langue des descriptions IA se règle séparément, donc vous pouvez lancer FlowShot en anglais et générer les guides en français, ou n'importe quelle combinaison.

---

## Démarrage Rapide

### Prérequis

- Node.js 22+
- [pnpm](https://pnpm.io) 10+
- Chrome, Firefox, Edge ou Brave (pour les tests)

### Installer

```bash
git clone <votre-url-de-repo>
cd flowshot
pnpm install
```

### Exécuter en Développement

```bash
pnpm dev                   # Chrome (MV3) avec HMR
pnpm dev:firefox           # Firefox (MV3) avec HMR
```

WXT lance une nouvelle instance du navigateur avec l'extension chargée.

### Construire

```bash
pnpm build                 # Chrome
pnpm build:firefox         # Firefox
pnpm zip:all               # Empaqueter les deux navigateurs
```

### Tester

```bash
pnpm test                  # Exécuter tous les tests
pnpm test:watch            # Mode watch
pnpm test:cov              # Rapport de couverture
```

### Lint et Formatage

```bash
pnpm lint                  # Vérifier
pnpm lint:fix              # Auto-correction
pnpm format                # Formatage uniquement
```

---

## Confidentialité et Stockage

Vos guides, étapes et captures vivent sur votre appareil. Pas de backend, pas de compte, pas de télémétrie. Vos clés API (si vous en utilisez) ne quittent jamais votre navigateur — elles sont stockées localement et utilisées pour appeler directement le fournisseur que vous avez choisi.

Deux choses quittent le navigateur : les icônes de sites sont récupérées via le service de favicons de Google, ce qui envoie le domaine du site, et les fonctions optionnelles d'IA et de voix envoient du texte ou de l'audio au fournisseur que vous avez configuré.

---

## Contribuer

Les contributions de toutes sortes sont les bienvenues : rapports de bugs, demandes de fonctionnalités, PRs et traductions.

Voir [CONTRIBUTING.md](./CONTRIBUTING.md) pour la configuration de développement, la structure du projet et les directives pour les contributeurs.

---

## Licence

Licence MIT

Copyright (c) 2026 Jojin John

Développé par Jojin John

Voir [LICENSE](./LICENSE) pour les détails.

---

<div align="center">

**Développé par [Jojin John](https://github.com/jojinjohn)**

</div>

<!-- LINK GROUP -->

[license-shield]: https://img.shields.io/badge/license-MIT-4F46E5?style=flat-square&labelColor=1E1B4B
[license-link]: ./LICENSE

[mv3-shield]: https://img.shields.io/badge/manifest-v3-3730A3?style=flat-square&labelColor=1E1B4B
[mv3-link]: https://developer.chrome.com/docs/extensions/mv3/intro/

[local-shield]: https://img.shields.io/badge/storage-100%25%20local-4F46E5?style=flat-square&labelColor=1E1B4B
[local-link]: #-confidentialité-et-stockage

[no-account-shield]: https://img.shields.io/badge/account-not%20required-4F46E5?style=flat-square&labelColor=1E1B4B
[no-account-link]: #-confidentialité-et-stockage
