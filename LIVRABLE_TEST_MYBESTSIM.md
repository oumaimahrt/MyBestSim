# 🚀 Dossier de Rendu – Test de Recrutement MyBestSim
**Candidature :** Stage Développeur IA & Automatisation (6 mois)  
**Candidate :** Oumaima Hrete  
**Date :** Octobre 2026  

---

## 📑 Sommaire
1. [Partie 1 : Data & Automatisation (Dashboard)](#partie-1--data--automatisation)
   - [Résultats des 6 Métriques Obligatoires](#les-6-métriques-obligatoires-vérifiées)
   - [Insights Clés & Découverte Data Engineering](#découverte-data-engineering-majeure)
   - [Fonctionnalités du Dashboard](#fonctionnalités-du-dashboard)
   - [Déploiement en Ligne (GitHub / Vercel / GitHub Pages)](#déploiement-en-ligne)
2. [Partie 2 : Contenu SEO (« Internet en croisière : quelle eSIM choisir ? »)](#partie-2--contenu-seo)
   - [Positionnement & Stratégie](#stratégie-et-intentions-de-recherche)
   - [Fichiers Livrés (.md et .html)](#fichiers-de-larticle)
3. [Partie 3 : Méthodologie & Usage de l'IA](#partie-3--paragraphe-usage-de-lia)
4. [Email Final Prêt à Envoyer à Etienne](#email-final-prêt-à-envoyer)

---

## 📊 Partie 1 : Data & Automatisation

### Les 6 Métriques Obligatoires (Vérifiées)

| # | Consigne du Test | Valeur Réelle | Détail & Précision Analytique |
|---|---|---|---|
| **1** | **Nombre total de cartes eSIM** | **5 056 offres** | 4 403 offres à volume fixe + 653 forfaits en data illimitée |
| **2** | **Nombre de produits à plus de 100 €** | **56 produits** | Forfaits 30 jours illimités (ex : 4S eSIM, Airalo, aloSIM, GigSky) |
| **3** | **Fourchette de prix globale** | **5.36 € à 154.63 €** | Min : 5.36 € (Mexique/Indonésie) · Max : 154.63 € (Holafly Monde illimité) *(max 99.39 € sur forfaits à volume fixe)* |
| **4** | **Moyenne de data (Go) par carte** | **14.49 Go** | Calculée sur les 4 403 forfaits à volume fixe (min : 1 Go, max : 50 Go) ; les forfaits illimités étant exclus pour ne pas fausser la moyenne |
| **5** | **Prix moyen global** | **29.30 €** | 24.63 € sur les forfaits à volume fixe · 60.81 € sur les forfaits illimités |
| **6** | **Répartition par fournisseur** | **18 fournisseurs** | Airalo (722), Ubigi (562), eSIMX (432), Saily (382), GigSky (342), Nomad (312), Instabridge (282), aloSIM (262), Holafly (242), Yesim (222), Jetpac (212), Truphone (202), JamboSIM (182), Flexiroam (172), Yatelo (162), Maya Mobile (152), Roamic (122), 4S eSIM (92) |

### 💡 Découverte Data Engineering Majeure
Lors de l'analyse initiale automatisée des 18 fichiers CSV, un piège classique s'est présenté : les forfaits à data illimitée (653 produits) avaient une cellule `data_gb` vide. Un parseur naïf filtrant les lignes sans valeur numérique aurait exclu 653 forfaits, arrivant à une conclusion erronée de 4 403 produits, 0 produit à plus de 100 € et un prix max de 99.39 €.  
Grâce à un contrôle rigoureux du dataset, nous avons identifié et valorisé ces forfaits :
- Traitement propre des 653 forfaits avec badge dédié `♾️ Illimité`.
- Isolement mathématique des statistiques globales vs offres à quota pour une transparence totale.

### 🌟 Fonctionnalités du Dashboard
- **Filtres avancés :** Fournisseur, Destination (54 pays/régions), Type de data (Tous / Quota 1-50 Go / Illimité), Réseau (4G/5G), Top-up, Prix max et forfaits > 100 €.
- **Filtres Préréglés Intelligents (Smart Presets) :** 5 boutons en 1 clic (Top Rapport Q/P, 5G Ultra-Rapide, Data Illimitée, Forfaits Premium > 100€, Tout afficher).
- **Recherche instantanée :** Barre de recherche en temps réel par pays, fournisseur ou SKU.
- **Export CSV intégré :** Bouton pour exporter les offres filtrées d'un clic (idéal pour les équipes internes).
- **Badge Meilleure Valeur :** Détection automatique du plan le plus rentable par destination.
- **Robustesse technique :** Double loader (chargement instantané via `data.json` avec fallback transparent sur PapaParse/CSV).

### 🛠️ Démarche & Workflow de Réalisation (Dashboard)

1. **Analyse exploratoire des données :**
   - Analyse personnelle et approfondie des 18 fichiers CSV pour comprendre le modèle de données, les concepts d'offres eSIM (volume fixe vs illimité, zones géographiques) et le positionnement produit de MyBestSim.
   
2. **Conception & Automatisation du Pipeline (`import_pipeline.py`) :**
   - Génération et itération du script d'automatisation en binôme avec l'IA pour automatiser le flux de traitement des données et la génération du dashboard.
   - Exécution du script avec la commande `python3 import_pipeline.py`, compilant les données et redirigeant automatiquement vers le dashboard en local.

   ![Étape 1 : Exécution du pipeline Python et première génération du dashboard](screenshots/1.png)

3. **Vérification croisée (Data QA & Rendu UI) :**
   - Contrôle rigoureux des calculs et métriques générés par l'IA (exactitude des 6 métriques obligatoires, gestion des anomalies sur les 653 forfaits illimités, validation des 56 offres > 100 €).
   - Audit visuel du premier rendu d'interface pour s'assurer que tous les graphiques, tris et filtres fonctionnent fidèlement.

   ![Étape 2 : Vérification des données et première interface utilisateur](screenshots/2.png)

4. **Refonte & Alignement avec l'Identité de Marque MyBestSim :**
   - Amélioration continue de l'expérience utilisateur (UX) et refonte complète de l'UI pour reprendre fidèlement la charte graphique officielle du site MyBestSim (logo officiel cliquable, couleurs bleu ciel `#0ea5e9`, vert émeraude `#10b981`, jaune `#ffcc00`, police Poppins, cartes de KPIs structurées, contrastes renforcés et labels directes sur les graphiques).

   ![Étape 3 : Résultat final aux couleurs officielles de MyBestSim](screenshots/3.png)

---

## ✍️ Partie 2 : Contenu SEO

### Sujet : « Internet en croisière : quelle eSIM choisir ? »

**Démarche Méthodologique & Rédaction :**
- **Analyse du besoin & cadrage :** Lecture attentive des consignes et identification des contraintes réelles du croisiériste (problématique haute mer vs escales).
- **Recherche sémantique & benchmark SEO :** Exploration des intentions de recherche Google et des questions fréquentes (*People Also Ask*, requêtes associées : `internet en croisière esim`, `wifi paquebot croisière`, `quelle esim pour une croisière`).
- **Définition des éléments techniques SEO :** Conception de la balise Title accrocheuse, méta-description orientée conversion, hiérarchie sémantique stricte (un seul H1, structure H2/H3 claire), balisage Schema.org JSON-LD FAQPage, et stratégie de liens d'affiliation intelligents.
- **Rédaction assistée par IA & ancrage data :** Co-rédaction avec un prompt IA approfondi en s'appuyant directement sur les données réelles du catalogue analysé en Partie 1 (GigSky Cruise, Airalo, Saily, Ubigi...).
- **Relecture critique & ton de marque :** Réécriture humaine pour garantir un ton chaleureux, transparent et accessible, parfaitement aligné avec la ligne éditoriale de MyBestSim.

**Angle Stratégique de l'Article :**
1. **La physique du réseau :** Pourquoi les eSIM terrestres classiques s'arrêtent à 12 milles des côtes.
2. **Le piège satellite (*Cellular at Sea*) :** Comment les factures à 1 000 € se produisent et comment s'en prémunir.
3. **Le combo gagnant :** eSIM Régionale pour les escales (90% du besoin réel) + Mode Avion en mer = 15-25 € pour toute la croisière au lieu de 200 €.
4. **Le cas GigSky Cruise :** La seule eSIM avec accords maritimes pour les voyageurs devant rester connectés au large.
5. **Comparatif complet des offres réelles :** Airalo, Saily, Ubigi, Holafly, Yesim, GigSky.
6. **Balises Schema.org FAQPage :** Intégrées pour capter les Rich Snippets Google et les réponses des moteurs IA (Google AI Overviews, ChatGPT).

**Liens & Formats Livrés :**
- 🌐 **Article en ligne (URL Optimisée SEO) :** [https://mybestsim-green.vercel.app/articles/internet-croisiere-quelle-esim-choisir](https://mybestsim-green.vercel.app/articles/internet-croisiere-quelle-esim-choisir)
- 📝 **Version Markdown pour CMS :** [`article/article_seo_croisiere.md`](article/article_seo_croisiere.md)
- 📄 **Version Web HTML intégrée :** [`article/article_seo_croisiere.html`](article/article_seo_croisiere.html)

---

## 🤖 Partie 3 : Méthodologie & Usage de l'IA

Chez MyBestSim, le travail quotidien s'effectue en binôme avec des agents IA. Voici comment ce test a été abordé :

1. **L'IA comme accélérateur de prototypage :** Exploration rapide de la structure des 18 CSV, génération du premier jet du script Python, maquettage dynamique Chart.js et extraction des intentions de recherche SEO.
2. **Le développeur comme pilote et garant métier :**
   - **Détection et résolution d'un biais critique de données :** L'analyse initiale automatisée avait ignoré les forfaits sans quota numérique (653 forfaits illimités), créant un faux résultat (0 produit > 100 €). Mon analyse critique a permis d'identifier la faille, d'adapter le pipeline et d'assurer une intégrité analytique absolue.
   - **Conception produit & UX :** Refonte complète de l'interface aux couleurs officielles de MyBestSim, intégration d'un comparateur interactif avec filtres multi-critères, recherche en temps réel et export CSV.
   - **SEO technique à haute valeur ajoutée :** Structuration de l'article autour de la véritable contrainte maritime, intégration du schéma JSON-LD FAQPage et configuration d'un slug SEO propre.

---

## ✉️ Email Final Prêt à Envoyer

**À :** `mybestsim.business@gmail.com`  
**Objet :** Test technique Stagiaire Développeur IA & Automatisation – Oumaima Hrete  

```text
Bonjour Etienne,

Merci pour ce test stimulant et très proche des réalités quotidiennes du produit MyBestSim.

Voici mes livrables pour l'ensemble des parties du test :

🔗 1. Dashboard Data & Automatisation
• Dashboard en ligne : https://mybestsim-green.vercel.app
• Code source GitHub : https://github.com/oumaimahrt/MyBestSim

Les 6 statistiques demandées y sont mises en valeur dès le premier coup d'œil, complétées par un comparateur interactif (recherche instantanée, filtres multi-critères, gestion des forfaits illimités, export CSV) et 5 graphiques d'analyse de marché Chart.js reprenant l'identité visuelle officielle de MyBestSim.
Un point marquant relevé lors du traitement des données : le catalogue compte 5 056 offres, dont 653 forfaits illimités. Les 56 produits à plus de 100 € se trouvent parmi ces forfaits illimités (allant jusqu'à 154,63 €), tandis que les forfaits à quota fixe plafonnent à 99,39 € avec une moyenne de 14,49 Go. Le pipeline et le dashboard distinguent clairement ces deux segments pour une rigueur analytique maximale.

📄 2. Article SEO : « Internet en croisière : quelle eSIM choisir ? »
• Article en ligne (Slug SEO) : https://mybestsim-green.vercel.app/articles/internet-croisiere-quelle-esim-choisir
• Formats Markdown et HTML disponibles dans le dépôt (/article).

L'article adopte le ton transparent et pratique de MyBestSim : il résout le vrai dilemme du voyageur (le piège méconnu du roaming maritime satellite à 1 000 € vs le coût du Wi-Fi à bord), détaille la stratégie "eSIM régionale en escale + mode avion en mer", compare les offres réelles de notre dataset (GigSky Cruise, Airalo, Saily, Ubigi, Holafly...), et intègre le balisage structuré Schema.org FAQPage (JSON-LD) pour ranker en Rich Snippets Google et dans les moteurs IA.

🤖 3. Sur l'utilisation de l'IA pendant le test :
J'ai abordé ce test en binôme avec un agent IA, exactement comme dans votre quotidien chez MyBestSim. L'agent a été un excellent accélérateur pour explorer les 18 fichiers CSV, prototyper l'interface et analyser la concurrence SEO. Mon rôle a été de piloter rigoureusement le processus : corriger le biais initial d'ingestion sur les forfaits illimités pour garantir la justesse des métriques, architecturer un dashboard résilient avec double chargement JSON/CSV, et orienter l'article SEO vers les véritables contraintes techniques maritimes.

Je reste à votre entière disposition pour échanger lors de l'entretien visio.

Bien cordialement,
Oumaima Hrete
Étudiante à 42 Lyon
Portfolio : https://oumaimahreteportfolio.vercel.app
GitHub : https://github.com/oumaimahrt
```


