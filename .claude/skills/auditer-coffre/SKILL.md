---
name: auditer-coffre
description: Auditer la santé du coffre veille — articles non rattachés à un thème, liens cassés, inbox qui déborde, récaps manquants, intégrité du Core. À utiliser quand André demande un audit / bilan de la veille.
---

# Auditer le coffre (veille)

## Contrôles
1. **Articles orphelins** : notes d'`Archive/` sans thème (`Core/`) ni récap rattaché.
2. **Métadonnées manquantes** : article sans `source`, `date`, `themes` ou `tier`.
3. **Liens cassés** : `[[…]]` vers des notes inexistantes.
4. **Inbox** : alerter si `00_Inbox/` traîne des articles non traités depuis > 1 semaine.
5. **Cadence** : récap hebdo manquant pour une semaine écoulée ; rétro mensuelle manquante
   pour un mois clos.
6. **Intégrité Core** 🔒 : modifications de `Core/` (doivent être rares et validées).

## Restitution
- Rapport synthétique par contrôle (compte + liste).
- **Proposer** des correctifs priorisés ; ne rien corriger sans validation.

## Garde-fous
- Audit = lecture seule par défaut. L'IA propose, l'humain décide.
