# ⚡ Volta · L'atlas de l'électricité européenne

**Union européenne et Royaume-Uni, de 1990 à 2026 : consommation, production, hydroélectricité, prix, marchés et énergéticiens cotés, réunis dans une seule application.**

🔗 **Application en ligne : [abdoulhamiddiallo.github.io/volta-electricite-europe](https://abdoulhamiddiallo.github.io/volta-electricite-europe/)**

---

## 📊 Dashboard Preview

👉 **[Ouvrir l'application](https://abdoulhamiddiallo.github.io/volta-electricite-europe/)** : accueil, consommation, production, hydroélectricité, prix et simulateur de facture, énergéticiens et fiches sociétés, face-à-face entre pays, fiches nationales.

Une page HTML unique (environ 2,4 Mo), sans serveur ni dépendance externe, consultable sur ordinateur comme sur téléphone, en thème clair ou sombre.

---

## 🏆 Key Results

| Indicateur | Valeur |
|---|---|
| Pays couverts | **31** : les 27 de l'UE, le Royaume-Uni, la Norvège, la Suisse et l'Islande |
| Profondeur historique | **36 ans** de séries annuelles (1990-2025) |
| Énergéticiens analysés | **29** groupes, dont 25 cotés, avec une fiche complète chacun |
| Cours de bourse | **un an de cours quotidiens** et **cinq ans de cours mensuels** par société |
| Centrales hydrauliques | **33** plus grandes centrales d'Europe, géolocalisées |
| Rubriques | **9** : accueil, consommation, production, hydroélectricité, prix, énergéticiens, face-à-face, pays, sources |

Quelques chiffres que l'application met en lumière :

- En 2025, l'**éolien et le solaire (846 TWh)** ont dépassé pour la première fois **le charbon, le gaz et le fioul réunis (810 TWh)** dans l'Union européenne.
- Le **charbon** est passé de **65 %** de l'électricité britannique en 1990 à **0,1 %** en 2025.
- Un **Norvégien** consomme **24 490 kWh** par an, **4 fois** la moyenne européenne, avec une électricité à **90 % hydraulique**.
- En **août 2022**, le prix de gros moyen en France a atteint **493 €/MWh**, contre **61 €** en moyenne sur 2025.
- Pour **3 500 kWh** par an, un ménage paie **1 415 €** en Irlande et **379 €** en Hongrie.

---

## 💼 Business Impact

- **Pour un analyste énergie ou un journaliste** : une vue consolidée de 31 systèmes électriques, comparables en un clic, avec des définitions homogènes.
- **Pour un investisseur** : un tableau de bord de 29 énergéticiens avec valorisation (VE/EBITDA, PER), rentabilité, endettement, dividende, notation de crédit et performance face à l'indice STOXX Europe 600 Utilities.
- **Pour un ménage** : un simulateur qui chiffre sa facture annuelle dans chaque pays européen à consommation égale.
- **Pour un décideur** : des face-à-face libres entre deux pays (ou un pays et l'UE) sur 15 indicateurs, de l'intensité carbone au prix de gros.

---

## 🧭 Executive Summary

**Volta** répond à une question simple : *d'où vient l'électricité de l'Europe, combien en consomme-t-on, combien coûte-t-elle et qui la produit ?*

| Rubrique | Contenu |
|---|---|
| **Accueil** | Chiffres clés UE et Royaume-Uni, courbes 1990-2025, mix 2025, marchés du jour, faits marquants |
| **Consommation** | Carte animée de 1990 à 2025 (total, par habitant, évolution), classements, trajectoires nationales, importateurs et exportateurs |
| **Production** | Mix par filière pour chaque pays, classement bas carbone, carte de l'intensité carbone, champions de l'éolien, du solaire et du nucléaire |
| **Hydroélectricité** | Capacités (212 GW dont 55 GW de stations de pompage), carte des grandes centrales, sécheresse de 2022, chantiers de pompage, galerie de barrages, repères historiques |
| **Prix** | Simulateur de facture, prix ménages et entreprises, prix de gros 2019-2025, crise de 2022 mois par mois, plafond Ofgem, heures à prix négatif, carbone et gaz |
| **Énergéticiens** | Carte boursière, cartes société avec cours sur un an, comparateur sur 18 indicateurs, performance sur cinq ans, valorisation, marges, dette, dividendes, investissements, parcs de production |
| **Fiche société** | Cours (1 mois à 5 ans) comparé à l'indice, fourchette 52 semaines, notation, portrait, identité, comptes 2021-2025, dividende, actionnariat, parc, répartition de l'EBITDA, plan stratégique, actifs phares, actualité |
| **Face-à-face** | Deux territoires au choix comparés sur 15 indicateurs et 36 ans |
| **Pays** | 31 fiches nationales : consommation, mix, prix, centrales et énergéticiens du pays |

Une recherche globale (touche `/` ou `Ctrl K`) retrouve instantanément pays, sociétés, centrales et thèmes.

---

## 🔄 Pipeline

```
Sources publiques ──► Collecte ──► Préparation (Python) ──► Modèle de données JSON ──► Rendu (JavaScript + SVG) ──► index.html
```

1. **Collecte** : séries annuelles d'électricité, prix Eurostat, plafonds Ofgem, prix de gros, capacités hydrauliques, rapports annuels des sociétés, cours de bourse quotidiens et mensuels.
2. **Préparation** : harmonisation des codes pays, reconstruction des agrégats UE manquants à partir des 27 pays, conversion des devises (GBP, CZK, PLN, DKK, NOK) au taux de référence de la BCE, calcul des ratios financiers.
3. **Modèle** : un objet de données compact par domaine (pays, prix, hydraulique, sociétés, cotations).
4. **Rendu** : bibliothèque graphique écrite pour l'application (courbes, aires empilées, barres, anneaux, carte d'Europe, carte boursière, nuages de points), sans dépendance.
5. **Assemblage** : polices, logos, drapeaux et photographies intégrés dans un seul fichier HTML.

---

## 🧬 Lineage

| Donnée | Source |
|---|---|
| Consommation, production par filière, intensité carbone, échanges | Ember, via Our World in Data |
| Prix de l'électricité des ménages et des entreprises | Eurostat (nrg_pc_204, nrg_pc_205) |
| Royaume-Uni : facture et prix unitaire | Ofgem (plafond de prix) |
| Suisse : tarif des ménages | ElCom |
| Prix de gros | Ember, SMARD, Bundesnetzagentur, OMIE, Nord Pool, Commission européenne, RTE |
| Carbone et gaz | Agence européenne pour l'environnement, ESMA, ICAP, Commission européenne |
| Hydroélectricité | IRENA, Eurostat, Centre commun de recherche de la Commission européenne, IHA, exploitants |
| Énergéticiens | Rapports annuels et communiqués de résultats 2021-2025, présentations aux investisseurs, agences de notation |
| Cours de bourse | Yahoo Finance (cours du 2 octobre 2026) |
| Logos, drapeaux, photographies | Wikimedia Commons (auteurs et licences crédités sur chaque photo), flag-icons |

---

## 🏗️ Architecture

```
volta-electricite-europe/
├── index.html          Application complète (données, styles, scripts, images intégrés)
└── README.md
```

- **Navigation** par rubriques avec liens profonds (`#hydro`, `#pays=FR`, `#societe=iberdrola`)
- **Graphiques** en SVG redimensionnés à la largeur de l'écran, info-bulles au survol et au toucher
- **Thèmes** clair et sombre, choix mémorisé
- **Mise en page adaptative** jusqu'à 390 px de large

---

## 🛠️ Tech Stack

| Couche | Outils |
|---|---|
| Préparation des données | Python, pandas, Pillow |
| Application | HTML5, CSS3, JavaScript sans framework |
| Visualisation | SVG généré en JavaScript, carte d'Europe en projection azimutale équivalente de Lambert |
| Typographie | Inter, Space Grotesk, JetBrains Mono (intégrées) |
| Contrôle qualité | Playwright (rendu de chaque page sur ordinateur et téléphone, en clair et en sombre) |
| Hébergement | GitHub Pages |

---

## ✅ Conclusion

Volta rassemble dans un seul écran ce qui est d'ordinaire dispersé entre agences statistiques, régulateurs, gestionnaires de réseau et rapports financiers. Chaque chiffre est daté et sourcé, chaque graphique se lit en quelques secondes, et chaque pays comme chaque société peut être exploré en profondeur.

---

## 💡 Final Thought

> L'électricité est la ressource la plus partagée d'Europe et l'une des plus mal connues. Rendre ses chiffres lisibles, c'est permettre à chacun de comprendre la transition énergétique au lieu de la subir.

**Construire pour explorer. Explorer pour comprendre. Et apprendre en chemin.**

---

**Abdoul Hamid Diallo** · Data Engineer · Microsoft Fabric, Azure, Power BI, SQL Server · [LinkedIn](https://www.linkedin.com/in/abdoul-hamid-diallo-fabric-data-engineer/)
