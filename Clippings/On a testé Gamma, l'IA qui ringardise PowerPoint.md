---
title: "On a testé Gamma, l'IA qui ringardise PowerPoint"
source: "https://www.journaldunet.com/intelligence-artificielle/1550807-on-a-teste-gamma-l-ia-qui-ringardise-powerpoint/#utm_source=MagNews&utm_medium=email&utm_campaign=IA_24/06/2026&een=22f4909cebb2401233ce0cd744e6b3c5&seen=2&gbmlus=18e2e4ec0b496555f351f959d37f4e9970508c210c9a5dc6ecdbde02e6453a98?gbmlus=18e2e4ec0b496555f351f959d37f4e9970508c210c9a5dc6ecdbde02e6453a98"
author:
  - "[[Evann Hislers]]"
published: 2026-06-24
created: 2026-06-25
description: "A partir d'un prompt, d'un PDF ou de notes de réunion, Gamma génère des présentations modifiables et exportables. Nous avons évalué la qualité des rendus, la souplesse de l'éditeur et les limites du format."
tags:
  - "clippings"
---
[![On a testé Gamma, l'IA qui ringardise PowerPoint](https://img-0.journaldunet.com/edd_ZPp26_oZnSrqNswPlh726Ps=/540x/smart/8d77f5bb16314a989967323dd8a55750/ccmcms-jdn/39540726.png)](https://img-0.journaldunet.com/YDEhc_CcdJ1dmzhijS-EXT3b7uU=/1500x/smart/8d77f5bb16314a989967323dd8a55750/ccmcms-jdn/39540726.png "© JDN")A partir d'un prompt, d'un PDF ou de notes de réunion, Gamma génère des présentations modifiables et exportables. Nous avons évalué la qualité des rendus, la souplesse de l'éditeur et les limites du format.

```js
Mission : Lire les fichiers locaux, recueillir mes préférences, puis générer une présentation via l'API Gamma selon la doc : https://developers.gamma.app/llms.txt

ÉTAPE 0 — Préférences obligatoires

Analyse le dossier courant et pose-moi uniquement ces questions en un seul message (sans valeurs par défaut) :

Format, ratio et nombre de cartes souhaités.

Export automatique (pptx, pdf, png ou aucun).

Mode de traitement du texte, densité, ton et audience cible.

Instructions spécifiques de contenu/mise en page.

Source des images (et style si IA).

Dossier de destination Gamma et thème à appliquer.

ETAPE 1 — Lecture des sources

Après mes réponses, lis les fichiers locaux pour structurer le contenu (ou utilise mes inputs si le dossier est vide). Sépare chaque section par \\---\\ pour le découpage Gamma.

ETAPE 2 — Payload JSON

Construis le JSON pour POST https://public-api.gamma.app/v1.0/generations via le header X-API-KEY (variable GAMMA_API_KEY, à demander si absente). Affiche le payload et attends ma confirmation avant l'envoi.

ETAPE 3 — Exécution & Polling

Envoie le POST, récupère le generationId.

Polle GET https://public-api.gamma.app/v1.0/generations/){generationId} toutes les 5s jusqu'à completed ou failed.

Stoppe et alerte immédiatement en cas d'erreur 402 ou 403.

ETAPE 4 — Résumé final

Affiche : Titre, nombre de cartes, crédits (consommés/restants), lien Gamma (gammaUrl) et lien de téléchargement (exportUrl si export choisi).
```