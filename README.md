# lab7
## 🔐 Analyse Dynamique Android avec MobSF (DIVA)

### 📌 Présentation

Ce projet présente une **analyse dynamique complète** d’une application Android en utilisant **MobSF (Mobile Security Framework)**.

L’objectif est d’analyser l’application vulnérable **DIVA (Damn Insecure and Vulnerable App)** dans un environnement contrôlé, en utilisant :
- Un émulateur Android rooté (AVD)
- MobSF via Docker
- Frida pour l’instrumentation
- Interception du trafic HTTPS

---

### 🎯 Objectifs

- Comprendre l’analyse **dynamique (runtime)** Android
- Configurer un **émulateur propre sans Google Play**
- Utiliser **MobSF avec Docker**
- Observer le comportement d’une application en temps réel
- Détecter des vulnérabilités comme :
  - Stockage non sécurisé
  - Secrets hardcodés
  - Intents non protégés
  - Fuites dans les logs

---

### 🧰 Prérequis

#### Matériel
- Processeur 64 bits
- Minimum 8 Go de RAM
- Connexion Internet

#### Logiciels
- Android Studio (dernière version)
- Android SDK Platform-Tools (ADB)
- Docker Desktop
- Git

---

### ⚙️ Installation

#### 1. Cloner MobSF

```bash
git clone https://github.com/MobSF/Mobile-Security-Framework-MobSF.git
cd Mobile-Security-Framework-MobSF
2. Créer un émulateur Android (AVD)
Dans Android Studio :

Tools → AVD Manager → Create Virtual Device

Choisir : Pixel 5 (ou similaire)

Image système :

Android API 29 ou 30

Sans Google Play

Architecture : x86_64

Nom recommandé :

MobSF_DIVA_API_30

##3. Lancer l’émulateur (rooté)
Linux / Mac

bash
./scripts/start_avd.sh MobSF_DIVA_API_30
Windows

bash
scripts\start_avd.ps1 MobSF_DIVA_API_30
Vérification :

bash
adb devices
Exemple de sortie :

text
emulator-5554 device
4. Lancer MobSF avec Docker
bash
docker pull opensecurity/mobile-security-framework-mobsf:latest
docker run -it --rm -p 8000:8000 \
-e MOBSF_ANALYZER_IDENTIFIER=emulator-5554 \
opensecurity/mobile-security-framework-mobsf:latest
⚠️ Remplacez emulator-5554 par votre identifiant réel.

Accès :

text
http://127.0.0.1:8000
Identifiants :

text
Username: mobsf
Password: mobsf
📱 Test avec DIVA
Télécharger l’APK
text
http://www.payatu.com/damn-insecure-and-vulnerable-app/
Analyse
Aller dans MobSF → Upload & Analyze

Importer diva.apk

Lancer :

text
Dynamic Analysis
MobSF va automatiquement :

Installer l’app

Lancer Frida

Configurer le proxy HTTPS

Monitorer le comportement

🔍 Analyse Dynamique
Fonctionnalités utilisées
📜 Runtime Logs (Logcat)

🌐 Trafic réseau HTTP/HTTPS

🧠 Frida (instrumentation)

📂 File Monitor

🔄 Intent Monitor

🧪 Vulnérabilités détectées
🔓 Stockage en clair

🔑 Secrets hardcodés

📡 Trafic non sécurisé

📢 Logs sensibles

🔁 Intents exploitables

🧠 Exemple Frida
javascript
Java.perform(function() {
    console.log("Hook actif !");
});
⚠️ Dépannage
Problème	Solution
Dynamic Analysis Failed	Vérifier que l’émulateur est lancé
adb ne détecte rien	Vérifier adb devices
Docker ne démarre pas	Vérifier Docker Desktop
Émulateur lent	Utiliser API 29 x86_64
📊 Résultat
MobSF permet :

Une analyse complète (statique + dynamique)

Une interception HTTPS

Une instrumentation avancée avec Frida

🚀 Améliorations possibles
Tester avec :

InsecureBankv2

AndroGoat

Automatiser avec Frida scripts

Intégrer dans CI/CD

📚 Ressources
MobSF Docs : https://github.com/MobSF/docs

DIVA GitHub : https://github.com/payatu/diva-android

👨‍💻 Auteur
Ziyad Daber
