# Baromètre 2026-2027 des TPE et Artisans en France (Conformité RGPD, SEO local, IA & Sanctions CNIL)

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.24284538.svg)](https://doi.org/10.5281/zenodo.24284538)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

> **Synthèse empirique (Open Data — Site Digital Pro) :**  
> En France métropolitaine, **52,9 % des sites de TPE** n'affichent aucune politique de confidentialité, **34,6 %** omettent les mentions légales obligatoires (LCEN) et **21,5 %** sont indisponibles ou en erreur technique (échantillon de **600 sites** issus d'OpenStreetMap, [Baromètre TPE 2026](https://sitedigitalpro.com/barometre-tpe-2026/)).  
> Sur **1 030 sites d'artisans du bâtiment** audités dans un **navigateur réel**, **77,3 %** ne déclarent pas leur activité en données structurées (`JSON-LD` métier), **83,2 %** n'ont pas de fichier `/llms.txt` et **40,4 %** n'offrent aucun numéro cliquable (`tel:`) sur mobile ([Baromètre Artisans Bâtiment](https://sitedigitalpro.com/barometre-artisans-batiment/)).  
> En parallèle, l'historique officiel des **395 sanctions prononcées par la CNIL (2011–2026)** cumule **1 118 238 301 €** d'amendes, dont **81,1 %** liés aux cookies et traceurs ([Baromètre Sanctions CNIL](https://sitedigitalpro.com/barometre-sanctions-cnil/)).

---

## Archive scientifique officielle & Sources

- **Dépôt scientifique CERN / Zenodo :** [https://doi.org/10.5281/zenodo.24284538](https://doi.org/10.5281/zenodo.24284538) (`https://zenodo.org/records/24284538`)
- **Portail général des études :** [https://sitedigitalpro.com/etudes/](https://sitedigitalpro.com/etudes/)
- **Étude 1 — Baromètre des TPE françaises (600 sites) :** [https://sitedigitalpro.com/barometre-tpe-2026/](https://sitedigitalpro.com/barometre-tpe-2026/)
- **Étude 2 — Baromètre des artisans du bâtiment (1 030 sites) :** [https://sitedigitalpro.com/barometre-artisans-batiment/](https://sitedigitalpro.com/barometre-artisans-batiment/)
- **Étude 3 — Baromètre des sanctions CNIL 2011–2026 (395 sanctions) :** [https://sitedigitalpro.com/barometre-sanctions-cnil/](https://sitedigitalpro.com/barometre-sanctions-cnil/)
- **Étude complémentaire — Visibilité IA des artisans :** [https://sitedigitalpro.com/barometre-ia-artisans/](https://sitedigitalpro.com/barometre-ia-artisans/)
- **Outils gratuits associés :**
  - Scanner de conformité RGPD : [https://rgpd-audit.com](https://rgpd-audit.com)
  - Test de visibilité Google & moteurs IA : [https://sitedigitalpro.com/test-visibilite-site/](https://sitedigitalpro.com/test-visibilite-site/)

---

## Chiffres clés vérifiés

### 1. Baromètre TPE France (N = 600 sites issus de 8 653 domaines OpenStreetMap)

| Indicateur | Résultat | Observation |
|---|---:|---|
| Disponibilité effective | **78,5 %** (471/600) | **21,5 %** inopérants (DNS, timeout, 404/5xx) |
| Chiffrement HTTPS *(répondants)* | **97,7 %** | 2,3 % en HTTP non sécurisé ; 2,8 % certificat invalide |
| Balise mobile (`viewport`) | **95,5 %** | Adaptation écran standardisée |
| Mentions légales (LCEN) | **65,4 %** | **34,6 %** sans mentions légales |
| Politique de confidentialité (RGPD) | **47,1 %** | **52,9 %** sans politique de confidentialité |
| Poids HTML médian | **115,4 Ko** | Charge initiale hors assets externes |
| Temps de réponse médian | **0,93 s** | Moyenne dégradée à `1,44 s` |

### 2. Baromètre Artisans du Bâtiment (N = 1 030 sites chargés dans un navigateur réel)

*Intervalle de confiance à 95 % : ± 2,6 points sur les totaux.*

| Indicateur | Sites (/ 1 030) | Pourcentage | IC 95 % |
|---|---:|---:|---|
| Pas de numéro SIRET affiché | 994 | **96,5 %** | [95,2 ; 97,5] |
| Pas de fichier `/llms.txt` | 857 | **83,2 %** | [80,8 ; 85,4] |
| A au moins un formulaire quelque part | 839 | **81,5 %** | [79,0 ; 83,7] |
| Pas de balisage d'activité (`JSON-LD` métier) | 796 | **77,3 %** | [74,6 ; 79,7] |
| Pas de politique de confidentialité | 657 | **63,8 %** | [60,8 ; 66,7] |
| Aucun lien e-mail (`mailto:`) | 636 | **61,7 %** | [58,7 ; 64,7] |
| Aucun numéro cliquable (`tel:`) | 416 | **40,4 %** | [37,4 ; 43,4] |
| Pas de mentions légales | 276 | **26,8 %** | [24,2 ; 29,6] |
| Aucun appel à l'action visible | 275 | **26,7 %** | [24,1 ; 29,5] |
| Débordement horizontal mobile | 188 | **18,3 %** | [16,0 ; 20,7] |
| Aucune page avec formulaire | 183 | **17,8 %** | [15,6 ; 20,2] |
| Pas en HTTPS | 1 | **0,1 %** | [0,0 ; 0,5] |

### 3. Baromètre Sanctions CNIL (N = 395 sanctions publiques, 2011 – 10/09/2026)

| Indicateur | Valeur |
|---|---:|
| Sanctions recensées | **395** *(dont 268 pécuniaires chiffrées)* |
| Montant cumulé hors astreintes | **1 118 238 301 €** *(1 123 589 051 € avec astreintes)* |
| Amende médiane / Amende maximale | **15 000 €** / **325 000 000 €** *(2025)* |
| Cookies & traceurs (part financière) | **907 074 000 € (81,1 %)** sur 73 dossiers (18,5 %) |
| Premier motif en fréquence | **Sécurité / violation de données** : 140 dossiers (**35,4 %**) |
| Concentration Top 10 amendes | **960 000 000 € (85,8 %)** |

---

## Contenu du dépôt

```text
.
├── CITATION.cff
├── LICENSE
├── README.md
├── datasets/
│   ├── barometre_tpe_2026_indicateurs_cles.csv
│   ├── barometre_tpe_2026_repartition_sectorielle.csv
│   ├── barometre_artisans_batiment_1030.csv
│   ├── barometre_artisans_batiment_metiers_osm.csv
│   ├── barometre_artisans_batiment_par_metier_serp.csv
│   └── barometre_sanctions_cnil_2011_2026_395.csv
└── rapports/
    ├── barometre_tpe_2026_rapport_scientifique.md
    ├── barometre_artisans_batiment_rapport_scientifique.md
    ├── barometre_sanctions_cnil_rapport_scientifique.md
    ├── zenodo.json
    ├── zenodo_artisans_batiment.json
    └── zenodo_sanctions_cnil.json
```

---

## Méthodologie et éthique des données

- **Mesures directes, aucune estimation :** chaque chiffre provient soit d'un crawl HTTP horodaté, soit d'un chargement complet dans un navigateur réel (DOM rendu, détecteurs étalonnés sur banc d'essai), soit de l'extraction des tableaux annuels publics de `cnil.fr`.
- **Aucune donnée personnelle ni désignation d'entreprise :** aucun nom de domaine, aucune raison sociale, aucun nom de dirigeant, email ou numéro de téléphone d'entreprise auditée n'est inclus dans les CSV publics.

---

## Comment citer ce travail

**Format texte (APA / journalistique) :**  
Lueger, S., & Site Digital Pro. (2026). *Baromètre 2026-2027 de la conformité numérique, technique et RGPD des TPE et artisans en France*. Zenodo (CERN). https://doi.org/10.5281/zenodo.24284538 — Source : https://sitedigitalpro.com/etudes/

**BibTeX :**
```bibtex
@misc{lueger_sitedigitalpro_2026_barometre,
  author       = {Lueger, St{\'e}phane and {Site Digital Pro}},
  title        = {{Barom{\`e}tre 2026-2027 de la conformit{\'e} num{\'e}rique, technique et RGPD des TPE et artisans fran{\c c}ais}},
  year         = {2026},
  publisher    = {Zenodo},
  doi          = {10.5281/zenodo.24284538},
  url          = {https://sitedigitalpro.com/barometre-tpe-2026/}
}
```
