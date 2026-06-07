# Rapport d'analyse de sécurité mobile

## A. Informations générales
- **Date**: 2026-06-07
- **Analyste**: Expert Developer
- **Cible**: My Application
- **Version/Hash**: 8CBB9F1CF1CD19580D5B8D05AFBF70859B6F1C1A8CA6A1235DCFD4E7B4569DD1
- **Outils utilisés**: BeVigil v2.1.0, Yaazhini v1.3.2

## B. Résumé exécutif
L'analyse de l'application "My Application" a révélé des faiblesses mineures dans la posture de sécurité, notamment l'activation des sauvegardes automatiques (Backup) et la désactivation des optimisations de code en mode release. Aucune clé API ou secret n'a été détecté dans le code source. Le niveau de risque global est considéré comme Faible après application des remédiations.

## C. Top 5 constats

### 1. Backup activé - FIND-003
- **Sévérité**: Medium
- **Preuve**: AndroidManifest.xml: line 7 (android:allowBackup="true")
- **Impact**: Extraction possible des données applicatives via adb backup.
- **Remédiation**: Défini android:allowBackup="false" dans le Manifest.
- **Référence OWASP**: MASVS-STORAGE-4

### 2. Optimisations désactivées en Release
- **Sévérité**: Low
- **Preuve**: build.gradle.kts (optimization { enable = false })
- **Impact**: Code plus facile à rétro-concevoir.
- **Remédiation**: Activé les optimisations R8.
- **Référence OWASP**: MASVS-CODE-1

### 3. Avertissement de syntaxe
- **Sévérité**: Info
- **Preuve**: MainActivity.kt (virgule de fin manquante)
- **Impact**: Aucun impact direct sur la sécurité, mais affecte la maintenabilité.
- **Remédiation**: Ajout de la virgule de fin.
- **Référence OWASP**: N/A

## D. Faux positifs notables
- Aucune clé API détectée malgré les alertes génériques sur les chaînes de caractères.

## E. Recommandations prioritaires
1. Désactiver allowBackup pour protéger les données locales.
2. Activer les optimisations de code en production.
3. Maintenir une hygiène de code stricte (trailing commas, etc.).

## F. Annexes
- [Lien vers triage.csv](../03-triage/triage.csv)
- [Mapping OWASP](../03-triage/owasp_mapping.md)
