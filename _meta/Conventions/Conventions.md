---
titre: Conventions du vault
type: doc
date_creation: 2026-05-07
date_maj: 2026-06-18
tags: [conventions, meta]
---

# 🗂️ Conventions du vault `obsidian_mtp`

> Index de référence pour la cohérence du vault. À consulter en cas de doute sur le frontmatter, le nommage ou le tagging.
>
> **Capitalisation des projets clients** (trois temps, statut épistémique, horizons, génération de contexte) : [[Capitalisation - projets clients]]. **Référence par champ et par type** : [[Frontmatter]].

## 0. Principe directeur

**Obsidian = valeur, pas gestion de projet.**

Une note n'a sa place dans le vault que si elle porte de la connaissance réutilisable. Si elle décrit une étape de pilotage, une décision opérationnelle non doctrinale, ou un suivi d'avancement, elle vit ailleurs (transcripts, .docx, Slack, mail, agenda) — ou, pour les projets clients, dans la **fiche projet**.

**Test de validation** pour toute note future : *« est-ce que ça portera encore de la valeur dans un an ? sur un autre projet ? sur le projet ? »* Si non → hors vault.

→ Détails et historique : [[_memoire/2026-05-21 - Refonte vault - spec|Refonte vault — spec 2026-05-21]] (structure), [[_memoire/2026-06-17 - Refonte capitalisation projets clients - spec|Refonte capitalisation — spec 2026-06-17]] (fond).

## 1. Architecture (PARA)

```
obsidian_mtp/
├── 00_Pilotage/        Daily, Inbox, navigation
├── 01_Projets/         Actif, deadline ou objectif
├── 02_Domaines/        Durable, sans fin nette
├── 03_Ressources/      Référence consultable, passive
├── 04_Archives/        Terminé ou inactif
└── _meta/              Templates, conventions, bases (caché du graphe)
```

## 2. Frontmatter par type de note

> Pour les **projets clients**, la référence détaillée par champ et par type — notes situées (`entretien`, `cartographie`, `note_reflexion`, `insight_projet`, `decision`), notes de domaine (`note_concept`, `note_solution`) et `fiche_projet` — vit dans [[Frontmatter]]. Les types généraux du vault sont ci-dessous.

### `home`
```yaml
---
titre: Home
type: home
date_creation: YYYY-MM-DD
tags: [home, navigation, racine]
---
```

### `moc` (projet, dossier, ou domaine)
```yaml
---
titre: MOC - <Nom>
type: moc
niveau: projet | dossier | domaine
projet: <slug>            # uniquement pour MOC de projet
statut: actif | dormant | archive
date_creation: YYYY-MM-DD
tags: [moc, <slug>, ...]
---
```

### `memoire_claude`
```yaml
---
type: memoire_claude
projet: <slug>
date: YYYY-MM-DD
session: <titre court>
tags: [memoire, <slug>, <thèmes>]
---
```

### `index_memoire`
```yaml
---
type: index_memoire
projet: <slug>
date_creation: YYYY-MM-DD
tags: [memoire, index, <slug>]
---
```

### `daily`
```yaml
---
type: daily
date: YYYY-MM-DD
tags: [daily]
---
```

### `evergreen` (note durable, autonome)
```yaml
---
titre: <affirmation claire>
type: evergreen
date_creation: YYYY-MM-DD
sources: []
tags: [evergreen, <thème>]
---
```

### `insight_projet` (constat atomique né d'un projet, à titre affirmatif)
```yaml
---
titre: <énoncé affirmatif court>
type: insight_projet
projet: <slug>
temps: diagnostic | analyse | synthese
date_creation: YYYY-MM-DD
revoir: true            # optionnel — constat à re-challenger
sources: []
tags: [insight, <slug>, <thèmes>]
---
```

> Le **type** porte le niveau épistémique : un insight est un *constat* par construction, il n'y a plus de champ `statut`. Un constat encore fragile se signale par `revoir: true`. La promotion vers un domaine est un **backlink** depuis une `note_concept` / `note_solution`, pas un champ. Cf. [[Capitalisation - projets clients]].

### `acteurs_projet` (annuaire des interlocuteurs d'un projet)
```yaml
---
titre: Acteurs - <Nom projet>
type: acteurs_projet
projet: <slug>
date_creation: YYYY-MM-DD
date_maj: YYYY-MM-DD
aliases: [<liste de tous les noms complets du projet>]
tags: [acteurs, annuaire, <slug>]
---
```

## 3. Nommage des fichiers

| Type | Pattern | Exemple |
|---|---|---|
| MOC | `MOC - <Nom>.md` | `MOC - Suivi MTP.md` |
| Fiche projet | `Fiche projet - <Nom>.md` | `Fiche projet - CD50 - référentiel bénéficiaires.md` |
| Mémoire Claude | `YYYY-MM-DD - <Thème>.md` | `2026-04-17 - RecapMaj v4.md` |
| Daily | `YYYY-MM-DD.md` | `2026-05-07.md` |
| Index mémoire | `INDEX.md` | `INDEX.md` |
| Evergreen | titre affirmatif | `Le refresh PowerQuery doit précéder l'exécution VBA.md` |
| Insight projet | titre affirmatif (≤ ~70 caractères, sans date, sans verbe modal) | `Le SNGI ne certifie que le volet PH.md` |
| Acteurs projet | `Acteurs.md` à la racine du projet | `Acteurs.md` |

**Règles** :
- Pas d'emoji dans les noms de fichiers (problèmes Windows + lisibilité)
- Pas de caractères spéciaux risqués (`/`, `\`, `:`, `?`, `*`, `"`, `<`, `>`, `|`)
- Espaces autorisés (Obsidian gère bien)
- Tirets cadratins `—` autorisés mais pas obligatoires

## 4. Tags

### Tags de statut (un seul à la fois)
- `#actif` — projet/note en cours
- `#dormant` — pas mort, pas actif (en pause)
- `#bloque` — bloqué par dépendance externe
- `#archive` — terminé, déplacé en `04_Archives/`

### Tags de type (souvent redondant avec frontmatter `type`)
- `#moc`, `#evergreen`, `#memoire`, `#daily`, `#ressource`

### Tags de domaine (transverses)
- `#metapolis`, `#men`, `#excel`, `#vba`, `#python`, `#powerquery`, `#powerbi`, `#obsidian`, `#claude`

### Tags-projet (préfixés)
- `#anarace/feature`, `#refmtp/scraping`, `#suivimtp/macro`

**Limite : ~15 tags transverses actifs maximum.** Au-delà, le système devient ingérable.

## 5. Liens internes

- **Toujours préférer le wikilink** `[[Note]]` à la mention textuelle
- **Lien avec alias** : `[[MOC - Suivi MTP|Suivi MTP]]`
- **Embed** (transclusion) : `![[Note]]` pour incruster une autre note
- **Embed Base** : `![[fichier.base]]`
- **Embed Canvas** : `[[fichier.canvas|texte alt]]` (les Canvas ne s'embeddent pas, on les linkise)

### Aliases YAML systématiques

Pour densifier le graphe et permettre `[[Léa Mathieu]]` ou `[[SNGI]]` en frappe libre :

- **Sur la note `Acteurs.md`** d'un projet : frontmatter `aliases: [Prénom Nom, Prénom Nom, ...]` listant toutes les personnes du projet. `[[Léa Mathieu]]` résout alors vers `Acteurs.md` (l'utilisateur navigue à la sous-section). Limite assumée : pas de lien à la sous-section directement.
- **Sur les notes-concept de domaine** (acronymes data, vocabulaire métier) : `aliases:` dans le frontmatter listant les variantes (`aliases: [SNGI, Système National de Gestion des Identifiants]`).
- **Format** : `aliases: [<alias 1>, <alias 2>, ...]` en YAML inline ou liste.

## 6. Écriture des notes — read-then-rewrite

Le `patch_vault_file` du MCP `obsidian-mcp-tools` est **abandonné** comme convention (juin 2026 — la pratique avait déjà basculé). On écrit en **read-then-rewrite** : `get_vault_file` puis réécriture complète via `create_vault_file`.

- Préserver **verbatim les block IDs `^slug`** (les liens en dépendent), notamment dans `Acteurs.md`.
- Corrections de typo = `Ctrl+H` dans Obsidian côté humain, pas via MCP.
- Le **MOC s'auto-construit** via les Bases (MOC-coquille + métadonnées) ; la condition est un frontmatter discipliné.

→ Détails : [[Capitalisation - projets clients]], [[_memoire/2026-06-17 - Refonte capitalisation projets clients - spec|spec juin 2026]].

## 7. Workflow type d'une note

```
┌──────────────┐     ┌──────────────┐     ┌──────────────┐
│  Capture     │ →   │  Distillation│ →   │ Capitalisation│
│  (Daily,     │     │  (Projet,    │     │  (Domaine,    │
│   Inbox)     │     │   Mémoire)   │     │   Evergreen)  │
└──────────────┘     └──────────────┘     └──────────────┘
```

Inspiré du cycle CODE de [BASB](03_Ressources/Méthodes%20PKM/02%20-%20Méthodes%20complètes/BASB.md) : **C**apture → **O**rganize → **D**istill → **E**xpress.

## 8. Liens

- [[Frontmatter]] — référence par champ et par type
- [[Capitalisation - projets clients]] — fond de la capitalisation projets clients
- [[Home]]
- [[02_Domaines/Système mémoire Claude/MOC - Système mémoire Claude|Système mémoire Claude]]
- [[03_Ressources/Méthodes PKM/00 - Index/Méthodes d'organisation personnelle, de prise de notes et de PKM|Index PKM v1.2]]
