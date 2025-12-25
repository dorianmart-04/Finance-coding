# Phoenix Autocall – Monte Carlo Pricing

## Objectif
Implémenter un pricing Monte Carlo simple d’un produit structuré de type Phoenix Autocall,
en simulant des trajectoires du sous-jacent et en appliquant les règles de rappel automatique,
de paiement de coupons avec effet mémoire et de protection du capital.

## Méthodologie
- Simulation de trajectoires du sous-jacent via un Geometric Brownian Motion (GBM)
- Vérification des barrières à chaque date d’observation :
  - barrière d’autocall
  - barrière de coupon avec effet mémoire
- Actualisation des flux
- Gestion du remboursement à maturité avec barrière de protection du capital (PDI)

## Technologies
- Python
- numpy

## Résultats
- Prix Monte Carlo du produit
- Erreur standard Monte Carlo
- Temps de calcul

