# 🔥 Pyrefighter V2 — Executive Summary

## London Fire Brigade Response Time Analysis (2009-2026)

> Analyse stratégique de 1.8 million d'interventions de la London Fire Brigade sur 17 ans, identifiant les zones géographiques prioritaires pour l'allocation des ressources opérationnelles.

---

## 🎯 Contexte

La London Fire Brigade (LFB) répond à environ 100 000 à 130 000 incidents par an à travers 33 boroughs. Son objectif officiel : arriver sur site en 6 minutes ou moins pour le premier véhicule.

Cette étude analyse **1 816 534 interventions** (2009-2026) pour évaluer la performance opérationnelle, identifier les inégalités territoriales et formuler des recommandations d'allocation de ressources.

---

## 📊 Résultats clés

### 1. Amplitude territoriale marquée
- **1.82 min d'écart médian** entre le borough le plus rapide (Kensington & Chelsea, 4.23 min) et le plus lent (Hillingdon, 6.05 min)
- Ratio 1.43× — environ 30 secondes d'écart moyen par intervention
- Pattern radial concentrique : cœur inner London performant, périphérie critique

### 2. Transformation du rôle de la LFB
- Part des incendies : 23.4% (2010) → 15.0% (2025), soit **-36%** grâce à la prévention
- Part des Special Services (secours à personne, désincarcération) : 24.0% → 38.0%, soit **+58%**
- La LFB devient un service d'urgence multi-risques, plus seulement anti-incendie

### 3. Détérioration structurelle post-COVID
- Médiane 2020 : 4.77 min (minimum décennal, effet lockdown)
- Médiane 2025 : 5.17 min (+8.4% depuis 2020, sans inflexion)
- Progression monotone depuis 2020 — la LFB perd du terrain

### 4. Impact quantifié des fermetures 2014
- Médiane 2013 : 4.83 min → 2015 : 5.17 min (+7% en 2 ans)
- 3 années pour revenir au niveau pré-fermetures

### 5. Volume opérationnel non-atteint
- **10 boroughs sur 33** dépassent 40% des incidents > 6 min
- **40,136 incidents/an** hors objectif dans le top 10 des boroughs prioritaires
- Soit environ 110 dépassements par jour

---

## 🚨 TOP 10 boroughs prioritaires (2023-2025)

| Rang | Borough | Incidents/an | Médiane | % > 6 min | Gap vs meilleur |
|------|---------|--------------|---------|-----------|-----------------|
| 1 | Hillingdon | 4,115 | 6.08 min | 51.5% | +1.78 min |
| 2 | Bromley | 3,640 | 5.83 min | 46.9% | +1.53 min |
| 3 | Richmond Upon Thames | 1,925 | 5.75 min | 44.9% | +1.45 min |
| 4 | Enfield | 3,645 | 5.73 min | 44.5% | +1.43 min |
| 5 | Havering | 2,720 | 5.68 min | 43.8% | +1.38 min |
| 6 | Redbridge | 2,810 | 5.63 min | 43.0% | +1.33 min |
| 7 | Brent | 4,069 | 5.62 min | 42.0% | +1.32 min |
| 8 | Bexley | 2,537 | 5.53 min | 40.8% | +1.23 min |
| 9 | Harrow | 2,238 | 5.6 min | 40.7% | +1.3 min |
| 10 | Barking And Dagenham | 2,430 | 5.58 min | 40.2% | +1.28 min |


---

## 🎯 Recommandations stratégiques

### Recommandation #1 : Investissement infrastructure OUEST
- Cible : Hillingdon (6.08 min), Brent, Harrow
- Justification : 4,742 incidents/an hors objectif
- Action : Nouvelle caserne ou repositionnement d'équipages

### Recommandation #2 : Renforcement zone SUD-EST
- Cible : Bromley (5.83 min), Bexley, Havering
- Justification : 3,934 incidents/an hors objectif
- Action : Nouvelle caserne au triangle Bromley-Bexley-Havering

### Recommandation #3 : Alerte précoce SUD-OUEST
- Cible : Richmond upon Thames, Kingston, Sutton
- Justification : Zone en dégradation post-COVID
- Action : Surveillance renforcée, plan d'action préventif

### Recommandation #4 : Étude du modèle SUTTON
- Contexte : Seul borough en amélioration (-3.9% depuis 2019)
- Action : Étude qualitative des leviers opérationnels réplicables

### Recommandation #5 : Adaptation aux Special Services
- Contexte : +14 points de Special Service en 15 ans
- Action : Investir dans le matériel adapté et former les équipes

---

## 📈 Méthodologie technique

- **Données** : 1.8M interventions LFB (2009-2026) + météo (Open-Meteo API) + démographie (London Datastore) + calendrier UK
- **Traitement** : Consolidation multi-sources (7 fichiers → Parquet 75 Mo)
- **Feature engineering** : 40 variables ML (temporelles, géographiques, distance stations, incidents, météo, population, holidays)
- **Modèles** : LightGBM régression + Quantile Regression (P10/P50/P90)
- **Pivot stratégique** : l'incertitude résiduelle du modèle prédictif (~3 min) étant incompatible avec un usage opérationnel en centre d'appel, le projet a pivoté vers un outil d'analyse territoriale d'aide à la décision publique

---

## 👤 Auteur

**Guillaume Blais** — Data & Marketing Automation Consultant  
Version originale (2022) : [Pyrefighter/Pyrefighter](https://github.com/Pyrefighter/Pyrefighter)
