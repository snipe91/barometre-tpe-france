# Baromètre 2026-2027 des Sites Web des Artisans du Bâtiment en France
## Audit empirique en navigateur réel sur 1 030 entreprises : visibilité Google, exploitabilité par les IA (GEO), conversion mobile et conformité légale

**Auteurs :** Stéphane Lueger — Site Digital Pro (Observatoire Numérique des TPE & Artisans)  
**Date de collecte :** 29 – 30 septembre 2026  
**Échantillon :** 1 030 sites web répondants sur 1 525 entreprises artisanales tirées au hasard depuis OpenStreetMap France  
**Marge d'erreur (IC 95 %) :** ± 2,6 points sur les totaux (environ ± 3,0 points autour de 50 %, ± 1,0 point autour de 5 % ou 95 %)  
**Licence :** Creative Commons Attribution 4.0 International (CC-BY 4.0)  
**Étude originale :** [Site Digital Pro — Baromètre des artisans du bâtiment](https://sitedigitalpro.com/barometre-artisans-batiment/)  
**Étude compagnon (DOI CERN/Zenodo) :** [Baromètre TPE 2026 (DOI 10.5281/zenodo.24284538)](https://doi.org/10.5281/zenodo.24284538)  
**Dépôt GitHub Open Data :** [snipe91/barometre-tpe-france](https://github.com/snipe91/barometre-tpe-france)

---

### Résumé Exécutif

Les sites web des artisans du bâtiment français remplissent-ils leur fonction première — être trouvés localement et générer des appels ou demandes de devis ? L'analyse de **1 030 sites web chargés dans un navigateur réel (inspection du DOM rendu)** met en évidence un décalage massif entre l'apparence des sites et leur exploitabilité commerciale et algorithmique :

- **77,3 % des sites (796 / 1 030 ; IC 95 % : [74,6 % ; 79,7 %])** ne déclarent pas leur activité en données structurées `JSON-LD` (`LocalBusiness`, métier, ville, téléphone). Si `70,5 %` embarquent du code `JSON-LD`, seuls **22,7 %** décrivent effectivement l'entreprise et sa zone d'intervention.
- **83,2 % (857 / 1 030 ; IC 95 % : [80,8 % ; 85,4 %])** ne disposent d'aucun fichier `/llms.txt` (`16,8 %` présent).
- **40,4 % (416 / 1 030 ; IC 95 % : [37,4 % ; 43,4 %])** n'affichent aucun numéro cliquable depuis smartphone (`tel:`), et **61,7 % (636 / 1 030)** n'offrent aucun lien `mailto:`.
- **81,5 % (839 / 1 030)** disposent d'un formulaire quelque part sur le site, mais **18,6 % (192 / 1 030)** n'en ont aucun sur la page d'accueil testée et **17,8 % (183 / 1 030)** n'ont aucune page avec formulaire de contact.
- **63,8 % (657 / 1 030 ; IC 95 % : [60,8 % ; 66,7 %])** n'affichent aucune politique de confidentialité et **26,8 % (276 / 1 030)** omettent les mentions légales obligatoires.

---

### 1. Méthodologie et Étalonnage

#### 1.1 Constitution de l'échantillon
1. Tirage aléatoire à graine fixe de **1 525 entreprises artisanales françaises** dans la base ouverte **OpenStreetMap** (tags `craft=*` du bâtiment : plombier, électricien, couvreur, menuisier, peintre, chauffagiste, carreleur, serrurier, charpentier, maçon, vitrier, etc.).
2. **1 030 sites web** ont répondu et ont été mesurés intégralement le 29 septembre 2026 dans le respect de la politesse réseau (délai de `1,5 s` entre requêtes, `5` requêtes simultanées maximum).
3. Un sous-échantillon complémentaire de **226 sites** issus des têtes de résultats sur 12 corps de métier (`barometre_artisans_batiment_par_metier_serp.csv`) permet de comparer les artisans visibles sur Google par métier.

#### 1.2 Pourquoi le DOM rendu dans un navigateur réel plutôt que le HTML brut
Une part importante des signaux commerciaux — formulaires injectés par JavaScript, boutons téléphone ou masquage CSS mobile — n'est pas fiable dans le HTML source brut. Sur l'indicateur « formulaire de contact », la comparaison préliminaire a montré un désaccord entre HTML brut et navigateur réel dans **55 %** des cas (avec **90 %** de faux positifs).

Chaque détecteur a été étalonné sur un banc d'essai (`banc_detecteurs.py`) validant qu'il rejette quatre détecteurs témoins défectueux (« toujours vrai », « toujours faux », « classe majoritaire », « aléatoire »). Les indicateurs « bannière de cookies » et « avis clients » ont été **volontairement exclus** de la publication parce que la détection lexicale des mots « cookie » ou « avis » ne garantit ni la conformité juridique de la bannière ni la présence d'avis clients réels.

#### 1.3 Confidentialité et absence de données nominatives
Le jeu de données public ne diffuse ni noms de domaines, ni raisons sociales, ni noms de dirigeants afin d'éviter toute désignation publique d'entreprises individuelles.

---

### 2. Résultats Détaillés sur les 1 030 Sites

#### 2.1 Tableau complet des 21 indicateurs mesurés (`barometre_artisans_batiment_1030.csv`)

| Indicateur | Libellé mesuré | Sites concernés (/ 1 030) | Pourcentage | IC 95 % |
|---|---|---:|---:|---|
| `siret` | Pas de numéro SIRET affiché | 994 | **96,5 %** | [95,2 ; 97,5] |
| `llms` | Pas de fichier `/llms.txt` | 857 | **83,2 %** | [80,8 ; 85,4] |
| `a_un_formulaire` | A au moins un formulaire sur le site | 839 | **81,5 %** | [79,0 ; 83,7] |
| `jsonld_metier` | Pas de balisage d'activité (JSON-LD métier) | 796 | **77,3 %** | [74,6 ; 79,7] |
| `politique` | Pas de politique de confidentialité | 657 | **63,8 %** | [60,8 ; 66,7] |
| `n_mailto` | Aucun lien e-mail (`mailto:`) | 636 | **61,7 %** | [58,7 ; 64,7] |
| `adresse` | Pas d'adresse postale complète | 478 | **46,4 %** | [43,4 ; 49,5] |
| `n_tel` | Aucun numéro cliquable (`tel:`) | 416 | **40,4 %** | [37,4 ; 43,4] |
| `mentions` | Pas de mentions légales | 276 | **26,8 %** | [24,2 ; 29,6] |
| `cta` | Aucun appel à l'action visible | 275 | **26,7 %** | [24,1 ; 29,5] |
| `canonical` | Pas d'URL canonique | 211 | **20,5 %** | [18,1 ; 23,1] |
| `n_champs` | Aucun champ de formulaire sur la page testée | 192 | **18,6 %** | [16,4 ; 21,1] |
| `deborde` | Contenu qui déborde horizontalement sur mobile | 188 | **18,3 %** | [16,0 ; 20,7] |
| `page_formulaire` | N'a aucune page avec formulaire | 183 | **17,8 %** | [15,6 ; 20,2] |
| `sitemap` | Pas de `sitemap.xml` déclaré | 177 | **17,2 %** | [15,0 ; 19,6] |
| `meta_desc` | Pas de meta description | 170 | **16,5 %** | [14,4 ; 18,9] |
| `h1_count` | Plusieurs balises H1 sur la même page | 156 | **15,1 %** | [13,1 ; 17,5] |
| `robots` | Pas de fichier `robots.txt` accessible | 131 | **12,7 %** | [10,8 ; 14,9] |
| `lang` | Pas d'attribut `lang` sur `<html>` | 47 | **4,6 %** | [3,4 ; 6,0] |
| `title` | Pas de balise `<title>` | 9 | **0,9 %** | [0,5 ; 1,7] |
| `https` | Site non servi en HTTPS | 1 | **0,1 %** | [0,0 ; 0,5] |

Signaux complémentaires relevés sur les 4 piliers de la page d'étude :
- **Balise `<title>` de longueur optimale (30–60 caractères) :** `45,8 %` (`99,1 %` présentent une balise `<title>`).
- **Meta description de longueur optimale (120–160 caractères) :** `50,2 %` (`83,4 %` dans le tableau synthèse / `16,5 %` absente dans l'extraction brute).
- **Structure H1 / H2 :** `68,9 %` ont un seul H1 unique ; `84,2 %` contiennent au moins deux H2.
- **JSON-LD technique vs métier :** `70,5 %` intègrent un script JSON-LD technique (souvent fil d'Ariane généré par le CMS), mais seulement `22,7 %` déclarent l'activité, la ville et le téléphone.

#### 2.2 Classement des 10 principaux corps de métier (corpus OpenStreetMap)

Critère composite d'invisibilité commerciale : sites cumulant **au moins 3 manques parmi 5** (absence de données structurées d'activité, absence de téléphone cliquable, absence de champ de formulaire, absence de `/llms.txt`, absence de meta description).

| Rang | Corps de métier | Sites mesurés | Sans balisage d'activité | Sans téléphone cliquable | Cumule ≥ 3 manques |
|---:|---|---:|---:|---:|---:|
| 1 | **Charpentier** | 138 | 79,7 % | 44,2 % | **52,9 %** |
| 2 | **Chauffagiste (CVC)** | 135 | 83,0 % | 37,0 % | **48,9 %** |
| 3 | **Menuisier** | 118 | 75,4 % | 39,8 % | **48,3 %** |
| 4 | **Peintre en bâtiment** | 57 | 77,2 % | 40,4 % | **47,4 %** |
| 5 | **Vitrier** | 114 | 77,2 % | 41,2 % | **46,5 %** |
| 6 | **Couvreur** | 78 | 79,5 % | 43,6 % | **46,2 %** |
| 7 | **Électricien** | 82 | 82,9 % | 42,7 % | **43,9 %** |
| 8 | **Maçon** | 154 | 72,1 % | 42,9 % | **39,6 %** |
| 9 | **Plombier** | 117 | 74,4 % | 33,3 % | **35,9 %** |
| 10 | **Serrurier** | 20 | 65,0 % | 30,0 % | **35,0 %** |

#### 2.3 Sous-échantillon complémentaire par métier (226 sites, `barometre_artisans_batiment_par_metier_serp.csv`)

| Métier | Sites mesurés | Sans tél. cliquable | Sans formulaire | Sans SIRET | Chargement médian |
|---|---:|---:|---:|---:|---:|
| Plombier | 29 | 31,0 % (9) | 58,6 % (17) | 79,3 % (23) | 0,9 s |
| Pisciniste | 28 | 25,0 % (7) | 53,6 % (15) | 96,4 % (27) | 1,2 s |
| Vitrier | 27 | 14,8 % (4) | 66,7 % (18) | 88,9 % (24) | 1,3 s |
| Électricien | 20 | 10,0 % (2) | 45,0 % (9) | 90,0 % (18) | 1,1 s |
| Charpentier | 19 | 42,1 % (8) | 78,9 % (15) | 89,5 % (17) | 0,9 s |
| Serrurier | 18 | 0,0 % (0) | 38,9 % (7) | 88,9 % (16) | 1,0 s |
| Couvreur | 16 | 12,5 % (2) | 50,0 % (8) | 93,8 % (15) | 1,3 s |
| Peintre | 16 | 37,5 % (6) | 68,8 % (11) | 100,0 % (16) | 1,4 s |
| Carreleur | 15 | 33,3 % (5) | 80,0 % (12) | 93,3 % (14) | 0,7 s |
| Chauffagiste | 14 | 42,9 % (6) | 35,7 % (5) | 85,7 % (12) | 1,6 s |
| Menuisier | 14 | 21,4 % (3) | 57,1 % (8) | 85,7 % (12) | 1,0 s |
| Maçon | 10 | 40,0 % (4) | 70,0 % (7) | 90,0 % (9) | 0,8 s |

---

### 3. Recommandations Opérationnelles

1. **Lien téléphone `tel:` et formulaire direct :** rendre le numéro cliquable dès le haut de page mobile (correction du manque touchant `40,4 %` des sites) et placer un accès direct au formulaire sur la page d'accueil.
2. **Balisage sémantique `LocalBusiness` complet :** déclarer métier exact, ville, zones d'intervention, numéro de téléphone et SIRET en `JSON-LD`.
3. **Conformité RGPD & LCEN dès la conception :** politique de confidentialité accessible et mentions légales complètes pour tout site équipé d'un formulaire (`63,8 %` d'absence de politique sur un parc où `81,5 %` collectent des demandes via formulaire).

---

### Références & Sources

- **Page d'étude complète :** [https://sitedigitalpro.com/barometre-artisans-batiment/](https://sitedigitalpro.com/barometre-artisans-batiment/)
- **Baromètre TPE 2026 (600 sites) :** [https://sitedigitalpro.com/barometre-tpe-2026/](https://sitedigitalpro.com/barometre-tpe-2026/) — DOI CERN/Zenodo : [10.5281/zenodo.24284538](https://doi.org/10.5281/zenodo.24284538)
- **Baromètre des sanctions CNIL :** [https://sitedigitalpro.com/barometre-sanctions-cnil/](https://sitedigitalpro.com/barometre-sanctions-cnil/)
- **Outil gratuit de diagnostic :** [https://sitedigitalpro.com/test-visibilite-site/](https://sitedigitalpro.com/test-visibilite-site/) et [https://rgpd-audit.com](https://rgpd-audit.com)
- **Dépôt GitHub Open Data :** [https://github.com/snipe91/barometre-tpe-france](https://github.com/snipe91/barometre-tpe-france)
