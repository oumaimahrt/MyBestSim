# 📡 MyBestSim – Test Technique Développeur IA & Automatisation

[![Author](https://img.shields.io/badge/Auteur-Oumaima%20Hrete-blue.svg)](https://oumaimahreteportfolio.vercel.app/)
[![GitHub](https://img.shields.io/badge/GitHub-oumaimahrt-181717.svg?logo=github)](https://github.com/oumaimahrt)
[![Status](https://img.shields.io/badge/Status-Livrable%20Termin%C3%A9%20%26%20Valid%C3%A9-success.svg)]()

Ce dépôt contient l'ensemble des livrables réalisés par **Oumaima Hrete** dans le cadre du test de recrutement pour le stage **Développeur IA & Automatisation (6 mois)** chez **MyBestSim**.

---

## 🌟 Liens Rapides des Livrables

- 🚀 **Dashboard interactif en ligne :** [Accéder au Dashboard Live](https://oumaimahrt.github.io/mybestsim-dashboard/dashboard/) *(ou en local sur `http://localhost:8080/dashboard/`)*
- 📄 **Article SEO complet (HTML) :** [`article/article_seo_croisiere.html`](article/article_seo_croisiere.html) *(ou en local sur `http://localhost:8080/article/article_seo_croisiere.html`)*
- 📝 **Article SEO (Markdown) :** [`article/article_seo_croisiere.md`](article/article_seo_croisiere.md)
- ⚙️ **Pipeline d'importation Python :** [`import_pipeline.py`](import_pipeline.py)
- 📋 **Dossier de rendu complet & Email :** [`LIVRABLE_TEST_MYBESTSIM.md`](LIVRABLE_TEST_MYBESTSIM.md)

---

## 📊 Partie 1 : Data & Automatisation

### Contexte & Mission
MyBestSim importe quotidiennement des offres eSIM via des fichiers CSV (un par fournisseur).  
L'objectif : concevoir une automatisation capable d'ingérer ces flux, d'extraire les métriques clés, et de générer un dashboard visuel accessible en ligne.

> **Note sur les données (`data/`) :** Ce dossier contient exclusivement des grilles tarifaires publiques issues des catalogues des 18 fournisseurs eSIM. Il ne comporte aucune donnée personnelle (zéro PII) ou confidentielle, garantissant une conformité totale tout en assurant la reproductibilité immédiate du pipeline en local.

### 🔍 Les 6 Statistiques Clés Requises (Catalogue de 5 056 Offres)

| # | Métrique Obligatoire | Valeur Réelle | Précision Analytique & Data Engineering |
|---|---|---|---|
| **1** | **Nombre total de cartes eSIM** | **5 056 offres** | 4 403 à quota fixe + 653 en data illimitée (18 fournisseurs, 54 destinations) |
| **2** | **Nombre de produits à plus de 100 €** | **56 offres** | Forfaits 30 jours illimités (4S eSIM, Airalo, aloSIM, GigSky) allant jusqu'à 154,63 € |
| **3** | **Fourchette de prix globale** | **5,36 € à 154,63 €** | Min : 5,36 € (Mexique/Indonésie) · Max : 154,63 € *(max 99,39 € sur forfaits quota)* |
| **4** | **Moyenne de data (Go) par carte** | **14,49 Go** | Calculée sur les 4 403 forfaits avec quota de données (1 à 50 Go) |
| **5** | **Prix moyen global** | **29,30 €** | 24,63 € (forfaits à volume fixe) · 60,81 € (forfaits illimités) |
| **6** | **Répartition par fournisseur** | **18 providers** | Airalo (722), Ubigi (562), eSIMX (432), Saily (382), GigSky (342), Nomad (312), Instabridge (282), aloSIM (262), Holafly (242), Yesim (222), Jetpac (212), Truphone (202), JamboSIM (182), Flexiroam (172), Yatelo (162), Maya Mobile (152), Roamic (122), 4S eSIM (92) |

### 🛠️ Architecture Technique & Valeur Ajoutée
1. **Pipeline d'importation robuste (`import_pipeline.py`) :**
   - Ingestion des 18 fichiers CSV avec gestion des encodages et détection des anomalies.
   - **Résolution du piège des données illimitées :** détection des 653 cellules vides sans quota pour éviter de tronquer les offres > 100 €.
   - Génération automatisée du fichier `dashboard/data.json` pour alimenter le front-end.
2. **Dashboard UI Premium (`dashboard/index.html`) :**
   - Dark Mode moderne avec glassmorphism inspiré des outils SaaS de référence.
   - 5 visualisations interactives Chart.js (parts de marché, prix au Go, taux 5G, top destinations).
   - Insights business orientés affiliation (notamment le décorrélation entre notoriété et prix au Go chez Airalo vs JamboSIM/Yesim).
   - Comparateur interactif : filtres multi-critères, recherche temps réel, gestion des forfaits illimités, et bouton d'**exportation CSV** des résultats filtrés.
   - **Double loader résilient :** chargement instantané en JSON avec fallback automatique sur PapaParse/CSV en cas de contrainte réseau.

```bash
# Pour exécuter le pipeline d'importation et mettre à jour les données :
python3 import_pipeline.py
```

---

## ✍️ Partie 2 : Création de Contenu SEO

### Sujet imposé : « Internet en croisière : quelle eSIM choisir ? »

L'article a été rédigé avec l'identité et le ton éditorial de MyBestSim (pratique, transparent, orienté voyageur et monétisé par affiliation intelligente) :
- **Analyse d'intention de recherche :** Résout le dilemme du croisiériste entre le Wi-Fi à bord onéreux (20 à 35 €/jour) et le hors-forfait maritime satellite pouvant dépasser 1 000 €.
- **Explication technique vulgarisée :** Distinction claire entre réseau maritime satellite en haute mer (> 12 milles des côtes) et réseaux cellulaires terrestres locaux lors des escales.
- **Stratégie recommandée :** eSIM Régionale en escale (90% du besoin) + Mode Avion en mer = 15 à 25 € pour toute la croisière.
- **Comparatif réel :** Zoom sur l'offre unique de **GigSky Cruise** (seule eSIM avec accords satellites maritimes sur 200+ navires) et des offres terrestres (Airalo, Saily, Ubigi, Holafly).
- **SEO & AI Visibility :** Balisage structuré **Schema.org FAQPage (JSON-LD)** intégré pour maximiser les chances d'affichage en Rich Snippets Google et l'indexation par Google AI Overviews et ChatGPT.

**Formats disponibles :**
- Version web mise en page prête pour WordPress : [`article/article_seo_croisiere.html`](article/article_seo_croisiere.html)
- Version Markdown : [`article/article_seo_croisiere.md`](article/article_seo_croisiere.md)

---

## 🤖 Partie 3 : Méthodologie & Usage de l'IA

Chez MyBestSim, le travail quotidien s'effectue en binôme avec des agents IA. Voici comment ce test a été abordé :
1. **L'IA comme accélérateur de prototypage :** Exploration rapide des structures CSV, prototypage CSS/JS réactif et benchmarking sémantique des intentions de recherche SEO.
2. **Le développeur comme garant de la rigueur et de la logique métier :**
   - **Correction du biais statistique :** L'analyse automatisée initiale avait évincé les forfaits sans volume numérique (les 653 forfaits illimités), créant un faux résultat (0 produit > 100 €). Mon intervention a permis d'isoler l'anomalie, d'adapter le pipeline et d'assurer une intégrité mathématique absolue.
   - **Conception produit orientée utilisateur :** Ajout de la recherche dynamique, du badge "🏆 Meilleur rapport qualité/prix" et de l'export CSV.
   - **Orientation SEO business :** Structuration de l'article autour des vraies contraintes de navigation maritime et intégration des données concrètes des 18 partenaires de la plateforme.

---

## 📂 Structure du Répertoire

```text
TEST_MyBestSim/
├── dashboard/
│   ├── index.html            # Dashboard web interactif (Dark UI, Chart.js, filtres, export)
│   └── data.json             # Dataset compilé et nettoyé (5 056 offres, 18 providers)
├── article/
│   ├── article_seo_croisiere.html  # Version web mise en page de l'article SEO
│   └── article_seo_croisiere.md    # Version Markdown prête pour publication
├── data/                     # Les 18 fichiers CSV originaux des fournisseurs
├── import_pipeline.py        # Script Python d'automatisation quotidienne de l'import
├── index.html                # Redirection racine vers le dashboard
├── LIVRABLE_TEST_MYBESTSIM.md# Dossier de synthèse complet et modèle d'email
└── README.md                 # Documentation globale du projet
```

---

## 👤 Contact
**Oumaima Hrete**  
- Étudiante à 42 Lyon (Niveau 16,72)  
- Portfolio : [oumaimahreteportfolio.vercel.app](https://oumaimahreteportfolio.vercel.app/)  
- GitHub : [github.com/oumaimahrt](https://github.com/oumaimahrt)  
- Email : `hreteoumaima@gmail.com`
