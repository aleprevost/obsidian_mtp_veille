---
titre: Conventions de frontmatter
type: note_meta
date_maj: 2026-06-18
tags: [meta, conventions, frontmatter]
---

# Conventions de frontmatter

Référence des champs par type de note. Le **type** porte le niveau épistémique ; il n'y a pas de champ `statut` pour le niveau (cf. brique 2).

## Notes situées (projet)

Portent toujours `projet` (slug). La plupart portent aussi `temps` (hérité du `temps_courant`) ; la `cartographie`, transverse et de référence, peut s'en dispenser.

| Type | Niveau épistémique | Champs obligatoires | Champs optionnels |
|---|---|---|---|
| `fiche_projet` | — (cadre) | `projet`, `client`, `mission`, `periode`, `statut`, `temps_courant`, `phase_courante`, `version`, `date_creation`, `date_maj` | — |
| `entretien` | information | `projet`, `temps`, `date`, `participants` | `service`, `participants_metapolis` |
| `note_reflexion` | hypothèse | `projet`, `temps`, `date_creation` | — |
| `insight_projet` | constat | `projet`, `temps`, `date_creation` | `revoir: true` (à re-challenger) |
| `decision` | décision | `projet`, `temps`, `source_cr`, `date_decision`, `date_creation` | — |
| `cartographie` | information | `projet` | `temps`, `source`, `date_maj` |

## Notes globales (domaine)

Portent `domaine`, jamais `projet`. Dégagées de tout situé (cf. brique 3).

| Type | Rôle | Champs obligatoires | Champs optionnels |
|---|---|---|---|
| `note_concept` | savoir transverse de référence | `domaine`, `date_creation`, `date_maj` | `aliases` |
| `note_solution` | fiche solution du marché (évaluative) | `domaine`, `editeur`, `categorie`, `modele`, `date_creation`, `date_maj` | `aliases` |

## Structurels (inchangés)

`moc` (point d'entrée projet/domaine), mémoire datée (`_Mémoire/`), MOC de domaine. Frontmatter existant conservé. S'y ajoutent `acteurs_projet` (annuaire projet : `projet`, `aliases`, block IDs `^slug` à préserver verbatim) et `contexte_mission` (proposition, remarques client : `projet`, sans `temps`).

## Conventions de valeurs

- **`type`** — liste fermée : `fiche_projet`, `entretien`, `cartographie`, `note_reflexion`, `insight_projet`, `decision`, `note_concept`, `note_solution`, `moc`, `acteurs_projet`, `contexte_mission`, `note_meta`.
- **`projet`** — **slug stable, minuscules-tirets**, fixé à l'initialisation (ex. `cr-sud-si-travaux`). Un seul slug par projet. C'est la clé de filtrage des Bases.
- **`temps`** — `diagnostic` | `analyse` | `synthese`. Hérité du `temps_courant` de la fiche projet à la création de la note.
- **`domaine`** — nom du domaine de rattachement (ex. `MDM et gouvernance data`).
- **`date`** — date de l'**événement** (entretien, séance). Format ISO `YYYY-MM-DD`.
- **`date_creation` / `date_maj`** — cycle de vie de la **note** (distinct de `date`).
- **`source_cr`** — wikilink vers le CR de COPIL. **Obligatoire** pour `decision` ; pas de CR → pas de décision.
- **`revoir`** — `true` pour signaler un constat à re-challenger (remplace l'ancien `statut: à challenger`).
- **`tags`** — tableau inline : `[<tag-de-type>, <slug-projet-ou-domaine>, <sujets>]`.

## Extensions de projet observées (à rationaliser)

Types apparus sur des projets spécifiques, conservés tels quels lors de la migration de juin 2026, à confirmer ou fondre dans la liste fermée :

- `atelier` — CR d'atelier de travail, proche d'`entretien` (porte `temps`, `date`, `statut`, participants). Cas : CR Sud - Ediflex.
- `note_doctrinale` — note de doctrine développée (niveau constat, mais forme longue, non atomique). Candidate à la promotion domaine. Cas : CD50, MESR Cloud.
- `matiere_documentation` — matière de livrable en construction. Cas : MESR Cloud.
- `note_reference` — note de référence projet. Cas : CR Sud - Ediflex.

## Promotion projet → domaine

Pas de champ. Un `insight_projet` « promu » est un Insight cité (backlink) depuis une `note_concept` ou `note_solution`. Requêtable en Base par présence du backlink domaine.

## Harmonisations à passer sur l'existant

1. `projet` : convertir les valeurs en nom complet vers le slug stable.
2. `insight_projet` : retirer le champ `statut` (le type porte le niveau).
3. Notes situées : ajouter `temps`.
4. `statut: à challenger` → `revoir: true`.
