# Moderne Svelte Aufgabenverwaltungs-App

Eine einfache und moderne Aufgabenverwaltungsanwendung, entwickelt mit dem Svelte-Framework für den persönlichen Gebrauch. 

## 🌐 Live Demo
Besuche die Live-Anwendung unter: [https://news-zi.netlify.app/](https://news-zi.netlify.app/)

## ✨ Features

- 🎨 Modernes und responsives UI-Design
- 📝 Aufgabenverwaltungssystem
- 📸 Fotogalerie
- 🎨 Farbwahlauswahl-Tool
- ⚡ Schnell und ressourcenschonend

## 🛠️ Technologiestack

- Svelte 3
- Svelte Materialify
- Rollup
- PostCSS
- SASS

## 🚀 Erste Schritte

### Voraussetzungen

- Node.js (v14 oder höher)
- npm (v6 oder höher)

### Installation

1. Repository klonen:
```bash
git clone https://github.com/djzh23/svelte-app.git
cd svelte-app

```

2. Abhängigkeiten installieren:
```bash
npm install
```

3. Sicherheitswarnungen beheben:
```bash
npm audit fix
```

4. Rollup-Plugins aktualisieren (falls erforderlich):
```bash
npm uninstall rollup-plugin-node-resolve rollup-plugin-commonjs
npm install --save-dev @rollup/plugin-node-resolve @rollup/plugin-commonjs
npm install
```

### Entwicklung

Um den Entwicklungsserver zu starten:

```bash
npm run dev
```

Die App ist dann unter `http://localhost:PORT` erreichbar.

## 📁 Projektstruktur

```
src/
├── components/
│   ├── layout/      # Layout-Komponenten
│   ├── features/    # Funktionsspezifische Komponenten
│   └── common/      # Wiederverwendbare Komponenten
├── peekComponents/  # Zusätzliche Komponenten
└── App.svelte       # Hauptkomponente der Anwendung
```

## 🚀 Deployment

Dieses Projekt ist für eine einfache Bereitstellung auf Netlify konfiguriert. Die Datei `netlify.toml`enthält die notwendigen Build-Einstellungen und Weiterleitungen.

## 🤝 Beiträge

Beiträge sind willkommen! Reiche gerne einen Pull Request ein.

