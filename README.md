# 🔐 LAB 8 — Analyse de posture et exposition d'applications mobiles avec BeVigil et Yaazhini

> Laboratoire pédagogique consacré à l'analyse défensive d'applications mobiles Android à l'aide des outils **BeVigil** et **Yaazhini**.

---

## 📖 Présentation

Ce laboratoire guide les étudiants à travers une méthodologie complète d'analyse de sécurité mobile, depuis la définition du périmètre jusqu'à la rédaction d'un rapport final.

L'objectif n'est **pas d'exploiter des vulnérabilités**, mais d'apprendre à :

- collecter des signaux d'exposition ;
- identifier des configurations à risque ;
- distinguer les faux positifs ;
- corréler les constats avec les standards OWASP ;
- produire un rapport professionnel exploitable.

---

## 🎯 Objectifs pédagogiques

À l'issue de ce TP, vous serez capable de :

- Définir un périmètre d'analyse conforme ;
- Organiser un audit défensif d'application mobile ;
- Utiliser BeVigil pour collecter des informations exposées publiquement ;
- Utiliser Yaazhini pour réaliser une analyse statique ;
- Identifier et trier les faux positifs ;
- Corréler les résultats avec les référentiels OWASP MASVS/MASTG ;
- Produire un rapport d'analyse structuré.

---

## ⚙️ Prérequis

- Connaissances de base en sécurité informatique ;
- Poste Windows avec accès Internet ;
- Accès aux outils **BeVigil** et **Yaazhini** ;
- Une cible explicitement autorisée :
  - APK pédagogique fourni ;
  - Application interne autorisée ;
  - Domaine validé par l'enseignant.

---

## ⚠️ Cadre légal et éthique

Ce laboratoire s'inscrit dans un **cadre strictement pédagogique et défensif**.

### ✅ Autorisé

- Analyse d'un APK fourni dans le cadre du cours ;
- Analyse d'une application interne autorisée ;
- Analyse d'un domaine explicitement approuvé.

### ❌ Interdit

- Exploiter les vulnérabilités découvertes ;
- Réaliser des tests intrusifs ;
- Contourner des mécanismes de sécurité ;
- Cibler des applications non autorisées ;
- Perturber ou surcharger une cible.

> Toute donnée sensible découverte doit être masquée dans les livrables.

---

## 📂 Structure du projet

```text
lab-mobile-security/
├── 00-scope/
├── 01-bevigil/
├── 02-yaazhini/
├── 03-triage/
├── 04-report/
├── analyse_info.txt
├── commands.log
└── checklist_fin.md
```

---

## 🛠️ Déroulement du laboratoire

### Task 0 — Définition du périmètre

Définir :

- la cible autorisée ;
- le propriétaire ;
- la preuve d'autorisation ;
- les limites de l'analyse.

**Livrable :**

```text
00-scope/scope.md
```

---

### Task 1 — Préparation du workspace

Créer :

- l'arborescence du projet ;
- les fichiers de traçabilité.

**Livrables :**

```text
analyse_info.txt
commands.log
```

---

### Task 2 — Préparation de l'artefact

#### Option A : APK pédagogique

- Copier l'APK ;
- Calculer son hash SHA-256 ;
- Documenter sa provenance.

#### Option B : Domaine autorisé

- Créer la liste des domaines autorisés.

**Livrables :**

```text
00-scope/application.apk
ou
00-scope/targets.txt
```

---

### Task 3 — Prise en main de BeVigil

Objectifs :

- créer un projet ;
- importer la cible ;
- explorer les résultats ;
- exporter les données.

**Livrable :**

```text
01-bevigil/bevigil_export.json
```

---

### Task 4 — Collecte avec BeVigil

Documenter :

- domaines ;
- sous-domaines ;
- endpoints ;
- URLs ;
- emails ;
- technologies détectées.

**Livrable :**

```text
01-bevigil/bevigil_notes.md
```

---

### Task 5 — Prise en main de Yaazhini

Objectifs :

- lancer l'analyse statique ;
- récupérer les rapports ;
- documenter l'environnement.

**Livrables :**

```text
02-yaazhini/[rapports]
```

---

### Task 6 — Analyse Yaazhini

Identifier notamment :

- secrets potentiels ;
- endpoints hardcodés ;
- permissions sensibles ;
- composants exposés ;
- configurations à risque.

> Aucun secret réel ne doit apparaître dans la documentation.

**Livrable :**

```text
02-yaazhini/yaazhini_notes.md
```

---

### Task 7 — Triage des constats

Consolider les résultats :

- suppression des doublons ;
- évaluation de la confiance ;
- classification par sévérité ;
- identification des faux positifs.

**Livrable :**

```text
03-triage/triage.csv
```

---

### Task 8 — Corrélation OWASP

Associer les constats aux référentiels :

- OWASP MASVS ;
- OWASP MASTG.

**Livrables :**

```text
03-triage/owasp_mapping.md
03-triage/triage.csv
```

---

### Task 9 — Rapport final

Rédiger un rapport contenant :

- résumé exécutif ;
- top 5 des constats ;
- faux positifs notables ;
- recommandations prioritaires ;
- annexes.

**Livrable :**

```text
04-report/rapport_final.md
```

---

### Task 10 — Vérification finale

Contrôler :

- la présence de tous les livrables ;
- l'absence de données sensibles ;
- la conformité du travail réalisé.

**Livrable :**

```text
checklist_fin.md
```

---

## 🔄 Workflow du laboratoire

```text
Définition du périmètre
          ↓
Analyse BeVigil
          ↓
Analyse Yaazhini
          ↓
Triage
          ↓
Normalisation
          ↓
Corrélation OWASP
          ↓
Rapport final
          ↓
Clôture
```

---

## 📦 Livrables attendus

### Traçabilité

- `analyse_info.txt`
- `commands.log`

### Périmètre

- `00-scope/scope.md`
- `00-scope/targets.txt` *(si applicable)*

### Analyse BeVigil

- `01-bevigil/bevigil_notes.md`
- Exports BeVigil

### Analyse Yaazhini

- `02-yaazhini/yaazhini_notes.md`
- Rapports Yaazhini

### Triage

- `03-triage/triage.csv`
- `03-triage/owasp_mapping.md`

### Reporting

- `04-report/rapport_final.md`

### Clôture

- `checklist_fin.md`

---

## 💡 Bonnes pratiques

- Respecter strictement le périmètre autorisé ;
- Documenter toutes les actions réalisées ;
- Distinguer faits et hypothèses ;
- Justifier les niveaux de sévérité ;
- Identifier et documenter les faux positifs ;
- Masquer systématiquement les données sensibles ;
- Produire des recommandations actionnables.

---

## 📚 Références

- OWASP MASVS
- OWASP MASTG
- Documentation BeVigil
- Documentation Yaazhini

---

## 🎓 Résultat attendu

À la fin de ce laboratoire, vous aurez réalisé une **analyse défensive complète d'une application mobile**, incluant :

- la collecte d'informations ;
- l'analyse statique ;
- le triage des constats ;
- la corrélation avec les standards OWASP ;
- la rédaction d'un rapport professionnel.

---

## 👨‍🏫 Informations

**Cours :** Sécurité des applications mobiles  
**Version :** 1.0  
**Auteur :** [Votre nom]  
**Licence :** Usage pédagogique uniquement.
