---
titre: Acteurs - {{nom_projet}}
type: acteurs_projet
projet: {{slug-projet}}
date_creation: {{date}}
date_maj: {{date}}
aliases: []
tags: [acteurs, annuaire, {{slug-projet}}]
---

# Acteurs — {{nom_projet}}

> Annuaire des interlocuteurs du projet. Une entrée = nom + direction/service + fonction. Pour ajouter une personne : `patch_vault_file` heading append sous le sous-heading de sa direction. Pour modifier une fonction : si le bloc a un `^id`, replace ciblé ; sinon réécriture du bloc concerné.

> **Aliases** : la liste `aliases:` du frontmatter doit lister toutes les personnes du projet (Prénom Nom complet). Permet `[[Léa Mathieu]]` en frappe libre, qui résout vers cette note.

> **Statut entretien** : suffixer la fonction par `— prévu` ou `— rencontré` quand le projet implique des entretiens. C'est le **seul élément de suivi conservé dans le vault** — pas de table de planification, pas de dates.

## Direction générale et DGA

- **{{Prénom Nom}}** — {{fonction}} — {{prévu / rencontré}} ^{{slug-personne}}

## {{Direction X}}

- **{{Prénom Nom}}** — {{fonction}} — {{prévu / rencontré}} ^{{slug-personne}}

## {{Direction Y}}

- **{{Prénom Nom}}** — {{fonction}} — {{prévu / rencontré}} ^{{slug-personne}}

## Liens

- [[01_Projets/{{slug-projet}}/MOC - {{nom_projet}}]]
