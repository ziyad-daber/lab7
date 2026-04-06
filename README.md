# 🔐 Analyse Dynamique Android avec MobSF (DIVA)

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Android-green?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Tool-MobSF-blue?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Analysis-Dynamic-red?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Status-Completed-success?style=for-the-badge"/>
</p>

---

## 📑 Table des matières

- Présentation
- Objectifs
- Prérequis
- Installation
- Test avec DIVA
- Analyse Dynamique
- Vulnérabilités
- Frida
- Dépannage
- Résultat
- Améliorations
- Ressources
- Auteur

---

## 📌 Présentation

Analyse dynamique d’une application Android vulnérable avec MobSF, Frida et interception HTTPS.

---

## 🎯 Objectifs

- Comprendre runtime Android  
- Observer comportement en temps réel  
- Identifier vulnérabilités  
- Utiliser Frida  
- Intercepter trafic  

---

## 🧰 Prérequis

- CPU 64 bits  
- 8 Go RAM  
- Android Studio  
- ADB  
- Docker  
- Git  

---

## ⚙️ Installation

### Cloner MobSF
```bash
git clone https://github.com/MobSF/Mobile-Security-Framework-MobSF.git
cd Mobile-Security-Framework-MobSF
```

### Créer un AVD
- Pixel 5  
- API 29 ou 30  
- Sans Google Play  
- x86_64  

Nom : MobSF_DIVA_API_30

### Lancer émulateur
```bash
./scripts/start_avd.sh MobSF_DIVA_API_30
```

### Vérifier
```bash
adb devices
```

### Lancer MobSF
```bash
docker pull opensecurity/mobile-security-framework-mobsf:latest
docker run -it --rm -p 8000:8000 -e MOBSF_ANALYZER_IDENTIFIER=emulator-5554 opensecurity/mobile-security-framework-mobsf:latest
```

---

## 📱 Test avec DIVA

Télécharger APK puis lancer Dynamic Analysis.

---

## 🔍 Analyse Dynamique

- Logcat  
- Network  
- Frida  
- File Monitor  
- Intent Monitor  

---

## 🧪 Vulnérabilités

- Stockage en clair  
- Secrets hardcodés  
- Trafic non sécurisé  
- Logs sensibles  
- Intents exploitables  

---

## 🧠 Exemple Frida
```javascript
Java.perform(function() {
    console.log("Hook actif !");
});
```

---

## ⚠️ Dépannage

- Vérifier émulateur  
- Vérifier adb  
- Vérifier Docker  

---

## 📊 Résultat

Analyse complète dynamique + statique.

---

## 🚀 Améliorations

- Tester autres apps  
- Automatiser  
- CI/CD  
- AI  

---

## 📚 Ressources

- MobSF Docs  
- DIVA GitHub  

---

## 👨‍💻 Auteur

Ziyad Daber
