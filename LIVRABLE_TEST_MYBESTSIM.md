# 🚀 Dossier de Rendu – Test de Recrutement MyBestSim
**Candidature :** Stage Développeur IA & Automatisation (6 mois)  
**Candidat(e) :** Oumaima Hrete  
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
- **Recherche instantanée :** Barre de recherche en temps réel par pays, fournisseur ou SKU.
- **Export CSV intégré :** Bouton pour exporter les offres filtrées d'un clic (idéal pour les équipes internes).
- **Badge Meilleure Valeur :** Détection automatique du plan le plus rentable par destination.
- **Robustesse technique :** Double loader (chargement instantané via `data.json` avec fallback transparent sur PapaParse/CSV).

---

## ✍️ Partie 2 : Contenu SEO

### Sujet : « Internet en croisière : quelle eSIM choisir ? »

**Angle Stratégique :**
L'article cible une requête à forte intention de recherche où les croisiéristes hésitent entre le Wi-Fi à bord (très cher, 20 à 35 €/jour) et le hors-forfait maritime satellite (pouvant dépasser 900 €).  
L'article démontre avec pédagogie :
1. **La physique du réseau :** Pourquoi les eSIM terrestres classiques s'arrêtent à 12 milles des côtes.
2. **Le piège satellite (*Cellular at Sea*) :** Comment les factures à 1 000 € se produisent et comment s'en prémunir.
3. **Le combo gagnant :** eSIM Régionale pour les escales (90% du besoin réel) + Mode Avion en mer = 15-25 € pour toute la croisière au lieu de 200 €.
4. **Le cas GigSky Cruise :** La seule eSIM avec accords maritimes pour les voyageurs devant rester connectés au large.
5. **Comparatif complet des offres réelles :** Airalo, Saily, Ubigi, Holafly, Yesim, GigSky.
6. **Balises Schema.org FAQPage :** Intégrées pour capter les Rich Snippets Google et les réponses IA (ChatGPT, Google AI Overviews).

### Fichiers Livrés
- **Markdown (.md) :** [`article/article_seo_croisiere.md`](file:///Users/mac/Desktop/TEST_MyBestSim/article/article_seo_croisiere.md) (prêt pour import WordPress, Notion ou Ghost)
- **HTML prêt à publier (.html) :** [`article/article_seo_croisiere.html`](file:///Users/mac/Desktop/TEST_MyBestSim/article/article_seo_croisiere.html) (avec styles MyBestSim, diagrammes, tableaux et responsive design)

---

## 🤖 Partie 3 : Paragraphe "Usage de l'IA"

> *À insérer dans le mail de rendu :*

```markdown
Sur l'utilisation de l'IA pendant ce test :
J'ai abordé ce test en binôme avec un agent IA, exactement comme au quotidien chez MyBestSim. 
L'agent m'a servi d'accélérateur sur l'exploration de données, le prototypage de l'interface et la veille concurrentielle SEO. Cependant, la valeur ajoutée a résidé dans le pilotage critique :
1. Détection d'un biais de données : l'analyse initiale avait exclu les forfaits illimités (cellules data_gb vides), ce qui masquait les 56 produits à plus de 100 €. J'ai identifié l'anomalie, corrigé le script d'ingestion pour séparer proprement forfaits à quota et forfaits illimités, et fiabilisé les métriques.
2. Architecture du dashboard : plutôt que de me contenter d'un script basique, nous avons conçu un outil complet (visualisations Chart.js, filtres multi-critères, recherche temps réel, export CSV, et loader résilient JSON/CSV).
3. Stratégie SEO : l'IA a permis d'extraire les intentions de recherche et d'analyser la concurrence sur la requête croisière. J'ai cadré la rédaction autour de la vraie problématique voyageur (le piège du roaming maritime satellite vs les escales), en intégrant les données réelles de nos 18 fournisseurs et le balisage Schema.org FAQPage.

Bilan : un livrable complet, testé et prêt pour la production en quelques heures, avec une vérification humaine rigoureuse à chaque étape.
```

---

## 📬 Déploiement en Ligne (2 minutes)

Pour mettre le dashboard en ligne et obtenir une URL publique :

### Option A : Déploiement GitHub Pages (Recommandé)
1. Crée un nouveau dépôt public sur GitHub nommé `mybestsim-dashboard`.
2. Dans ton terminal, pousse le code :
   ```bash
   cd /Users/mac/Desktop/TEST_MyBestSim
   git remote add origin https://github.com/oumaimahrt/mybestsim-dashboard.git
   git branch -M main
   git push -u origin main
   ```
3. Sur GitHub : **Settings > Pages > Branch: main / root > Save**.
4. Ton lien live sera disponible à l'adresse : `https://oumaimahrt.github.io/mybestsim-dashboard/dashboard/`

### Option B : Déploiement Vercel
1. Va sur [vercel.com](https://vercel.com) > **Add New Project** > Importer le repo GitHub.
2. Cliquer sur **Deploy**.
3. Ton lien live sera du type : `https://mybestsim-dashboard.vercel.app`

---

## ✉️ Email Final Prêt à Envoyer

**À :** `mybestsim.business@gmail.com`  
**Objet :** Test technique Stagiaire Développeur IA & Automatisation – Oumaima Hrete  

```text
Bonjour Etienne,

Merci pour ce test stimulant, très proche des réalités quotidiennes du produit MyBestSim.

Voici mes livrables pour les deux parties du test :

🔗 1. Dashboard Data & Automatisation
• Dashboard en ligne : [COLLER ICI TON LIEN VERCEL OU GITHUB PAGES]
• Code source GitHub : [COLLER ICI LE LIEN DU REPO GITHUB]

Les 6 statistiques demandées y sont mises en valeur dès le premier coup d'œil, complétées par un comparateur interactif (recherche instantanée, filtres multi-critères, export CSV) et des graphiques d'analyse de marché.
Un point intéressant relevé lors du traitement des données : le catalogue compte 5 056 offres, dont 653 forfaits illimités. Les 56 produits à plus de 100 € se trouvent parmi ces forfaits illimités (allant jusqu'à 154,63 €), tandis que les forfaits à volume défini plafonnent à 99,39 € avec une moyenne de 14,49 Go. Le dashboard distingue clairement ces deux segments pour une rigueur analytique maximale.

📄 2. Article SEO : « Internet en croisière : quelle eSIM choisir ? »
• L'article complet prêt à publier est disponible au format Markdown et HTML dans le dépôt (dossier /article).
• J'ai également préparé une version web mise en page prête à l'emploi.
L'article adopte le ton transparent et pratique de MyBestSim : il résout le vrai dilemme du voyageur (le piège méconnu du roaming maritime satellite à 1 000 € vs le coût du Wi-Fi à bord), détaille la stratégie "eSIM régionale en escale + mode avion en mer", compare les offres réelles de notre dataset (GigSky Cruise, Airalo, Saily, Ubigi...), et intègre le balisage Schema.org FAQPage pour ranker en haut de Google et dans les réponses IA.

🤖 3. Sur l'utilisation de l'IA pendant le test :
J'ai abordé ce test en binôme avec un agent IA, exactement comme dans votre quotidien. L'agent a été un excellent accélérateur pour explorer les 18 fichiers CSV, prototyper l'interface et analyser la concurrence SEO. Mon rôle a été de piloter rigoureusement le processus : corriger le biais initial d'ingestion sur les forfaits illimités pour garantir la justesse des métriques, architecturer un dashboard résilient avec double chargement JSON/CSV, et orienter l'article SEO vers les véritables contraintes techniques maritimes.

Je reste à votre entière disposition pour échanger lors de l'entretien visio.

Bien cordialement,
Oumaima Hrete
+33 6 XX XX XX XX
Portfolio : https://oumaimahreteportfolio.vercel.app
GitHub : https://github.com/oumaimahrt
```
