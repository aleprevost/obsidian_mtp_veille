---
titre: Capitalisation - projets clients
type: note_meta
date_maj: <YYYY-MM-DD>
tags: [meta, conventions, capitalisation, projets-clients]
---

# Capitalisation — projets clients

Règles de capitalisation du coffre pour les missions de conseil en transformation numérique. Voir [[Conventions - Frontmatter]] pour les champs, et `_meta/Templates/` pour les modèles de notes.

## Principe directeur

Le coffre n'est pas une archive, c'est un **instrument de travail vivant**. Son but : produire à la demande un contexte calé sur l'avancement (COSUI, COPIL, livrable, brief pour un autre LLM), pendant la mission autant qu'après.

Deux disciplines de fond :

- **Valeur, pas pilotage.** Ce qui aide à comprendre et à décider entre au coffre. La planification fine reste dehors. Le déroulé léger (entretiens/ateliers faits et à venir) est toléré, dans la fiche projet, parce qu'il aide à préparer.
- **Rien de définitif trop tôt.** En phase de découverte, on cherche à comprendre. Une parole d'entretien est une information, pas une décision. On retient beaucoup, on acte peu.

## Le modèle en trois temps

Toute mission, quel que soit son découpage en phases, se ramène à trois temps. C'est l'axe de capitalisation, comparable d'un projet à l'autre.

| Temps | Ce qu'on y fait | Ce qu'on capitalise | Horizon |
|---|---|---|---|
| **Diagnostic** | état des lieux, comprendre | acteurs, organigramme, process, difficultés, irritants | local |
| **Analyse** | besoins, benchmark, règles | besoins, règles de gestion, pistes, retex, solutions du marché | local |
| **Synthèse** | scénarios, feuille de route, CdC, specs | scénarios, et remontée globale : solutions, process types, modèles, RGPD | local → global |

Le pilotage (COPIL/COSUI) n'est pas un temps : ce sont les modalités de suivi, et le seul lieu où naissent les décisions.

## Brique 1 — Initialisation

À l'ouverture d'un projet :

1. **Lire la proposition** et en extraire identité (client, objet, mission, période), enjeu-clé, phases avec livrables et jalons, modalités de suivi.
2. **Mapper chaque phase concrète sur un temps** (diagnostic / analyse / synthèse). Une phase « pilotage » alimente *Suivi de mission*, pas un temps. Une phase peut recouvrir plusieurs temps.
3. **Soumettre le mapping** et attendre validation — il ne se déduit pas mécaniquement.
4. **Créer la fiche projet** (`Fiche projet - <Nom>.md`, modèle `Template - Fiche projet`) et la structure minimale si le projet est neuf (MOC, `Acteurs.md`, `Insights/`, `_Mémoire/INDEX.md`).

La fiche projet est **vivante et versionnée**. Glissement de jalon, statut de phase : à la volée. Changement de structure (phase ajoutée/fusionnée, livrable retiré) : signalé avant application, idéalement adossé à un COPIL.

## Brique 2 — Statut épistémique

Le **type de note porte le niveau**. Pas de champ `statut` pour l'épistémique.

| Niveau | Type de note | Comment on y monte |
|---|---|---|
| information | `entretien`, `cartographie` (matière) | par défaut à la captation |
| hypothèse | `note_reflexion` | quand une lecture est formulée |
| constat | `insight_projet` | recoupement (≥ 2 sources / atelier) **+ validation** |
| décision | `decision` (+ `source_cr`) | **uniquement un CR de COPIL** |

**Règle d'or : ne jamais faire monter un contenu d'un cran tout seul.** Une hypothèse ne devient Insight que recoupée et validée. Un constat ne devient décision que sur production du CR — sinon il reste constat, et le manque est signalé.

Distinction à tenir : la **décision** engage le client et se trace à un CR ; un parti pris technique ou méthodologique solide n'est qu'un **constat de doctrine** (`insight_projet`), même s'il est verrouillé.

Drapeau : un constat à re-challenger porte `revoir: true` (sans changer de nature).

## Brique 3 — Deux horizons

| | Local | Global |
|---|---|---|
| Type | `insight_projet` (situé) | `note_concept`, `note_solution` (transverse) |
| Vit dans | `01_Projets/<projet>/Insights/` | `02_Domaines/<domaine>/` |
| Contient | noms, dates, acteurs du client | concept, modèle, règle — **dégagés du contexte** |

**Promotion** (geste, pas statut). Critère : « est-ce que ça aiderait sur un autre projet, sans rien savoir de ce client ? ». Si oui, trois temps : **généraliser** (extraire le pattern) → **nettoyer** (sans nom d'agent ni date de séance) → **relier** (la note de domaine cite ses cas-sources projet). L'Insight projet reste local.

`promu` = un `insight_projet` qui a un backlink depuis une note de domaine. Pas de champ.

**Hygiène domaine** : une `note_concept` / `note_solution` ne porte pas de situé-projet dans son corps. Le situé reste dans l'Insight, référencé par lien ; le déroulé (« DPO présente 9h-11h ») n'a rien à y faire.

Quand : un peu en continu si un constat est manifestement transverse, surtout **en fin de phase 3 / fin de projet** (capitalisation globale).

## Génération de contexte à la demande

Chaque besoin définit un filtre : jusqu'où dans le projet (temps), et quel niveau épistémique passe.

| Besoin | Je pioche | Niveau laissé passer |
|---|---|---|
| Brief COSUI | phase courante, déroulé à venir, questions ouvertes | information à recouper → constat |
| Brief COPIL | constats consolidés, scénarios, décisions, points à trancher | constat + décision |
| Socle de livrable | constats, besoins, règles, solutions du marché | constat + décision |
| Contexte pour un autre LLM | tout : fiche, acteurs, matière, constats, décisions | tout, **étiqueté** par niveau et temps |

**Règle d'or de sortie : ne jamais élever le niveau d'un contenu en le restituant.** Une information reste annoncée comme information, même dans un brief de COPIL (« à consolider »).

Bénéfice : préparer un contexte, c'est aussi **lister les trous** — avant un COPIL, les constats prêts *et* les sujets encore trop verts à consolider avant l'échéance.

Mécanique : lire la fiche projet (où on en est) → appliquer le filtre du besoin → piocher par `projet` + `temps` + type via les Bases → composer.
