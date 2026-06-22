---
type: moc
tier: core
---

# MOC — Veille

Point d'entrée du coffre de veille.

## Niveaux
- 🔒 [[_LISEZ-MOI Core]] — règles du Core
- `00_Inbox/` — articles bruts à trier (web clipper)
- `Recall/` — récap hebdo + tendances en cours
- `Archive/` — articles capitalisés, par mois

## Thèmes suivis
> À renseigner : les axes de veille durables (ex. IA & service public, souveraineté
> numérique, open source, financement public du numérique…).

## Rétrospectives mensuelles
> Liens vers les rétros mensuelles (`Core/`), une par mois.

## Récaps hebdomadaires
```dataview
TABLE semaine, date
FROM "Recall"
WHERE type = "recap_hebdo"
SORT date DESC
```
