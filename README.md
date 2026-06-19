<div align="center">

# 📱 Kusel

**A community, tourism & civic-participation app — keeping the Kusel district connected, informed, and engaged.**

[![Flutter](https://img.shields.io/badge/Flutter-3.32.0-02569B?style=flat-square&logo=flutter&logoColor=white)](https://flutter.dev)
[![Dart](https://img.shields.io/badge/Dart-3.x-0175C2?style=flat-square&logo=dart&logoColor=white)](https://dart.dev)
[![Firebase](https://img.shields.io/badge/Firebase-enabled-FFCA28?style=flat-square&logo=firebase&logoColor=black)](https://firebase.google.com)
[![License](https://img.shields.io/badge/License-EUPL%201.2-green?style=flat-square)](LICENSE)
[![Platform](https://img.shields.io/badge/Platform-Android%20%7C%20iOS-lightgrey?style=flat-square)](#)

_Template C reference application — open-sourced from **KODI-Kommunen-Digital**. Licensed under the [EUPL-1.2](LICENSE)._

<br/>

[🇬🇧 English](#-english) &nbsp;·&nbsp; [🇩🇪 Deutsch](#-deutsch)

</div>

---

## 🇬🇧 English

### What is Kusel?

**Kusel** is a Flutter-based mobile application for the Kusel district. It combines local community life, tourism, mobility, and civic participation in one app — events, places, municipal services, and citizen engagement, with offline support and an interactive map.

---

### ✨ Features

| Feature | Description |
|---|---|
| 🗓️ **Events & Calendar** | Browse local events, listings, and highlights by category |
| 🧭 **Tourism & Explore** | Discover places of interest ("Mein Ort"), tourism content, and highlights |
| 🚌 **Mobility** | Local mobility information and services |
| 🏛️ **Virtual Town Hall** | Digital municipal services and council information |
| 🗳️ **Citizen Participation** | "Participate" flows — feedback, proposals, and municipal party info |
| 🗺️ **Interactive Map** | OpenStreetMap-based location search, pick, and compass navigation |
| 🏘️ **Multi-Municipality** | Browse and favourite municipalities and cities across the district |
| 📷 **QR Scanner** | In-app QR / barcode scanning |
| 🎬 **Media** | Image galleries and in-app video playback |
| 📴 **Offline Mode** | Hive-cached content + offline routing when no network is available |
| 🌐 **Localisation** | Multi-language UI with in-app translation |

---

### 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Framework | Flutter (Dart), FVM-pinned `3.32.0` |
| Navigation | GoRouter (`go_router`) + offline router |
| State | Provider-based (`providers/`) |
| Networking / Config | `flutter_dotenv` (`.envKusel`) |
| Local storage / Offline | Hive |
| Maps & Location | `flutter_map`, `open_street_map_search_and_pick`, `geolocator`, `flutter_compass`, `geocoding` |
| Push notifications | Firebase Cloud Messaging + `flutter_local_notifications` |
| Analytics | Matomo (`matomo_tracker`) |
| Media | `video_player`, `cached_network_image`, `mobile_scanner` (QR) |
| Responsive UI | `flutter_screenutil` |

---

### 🚀 Getting Started

> **Note:** Several configuration files are **not included** in this repository for security reasons.
> Obtain them from a teammate or your secure secrets vault, then follow every step below before running the app.

---

#### Step 1 — FVM (Flutter version)

This project pins its Flutter SDK with [FVM](https://fvm.app/) (`3.32.0`).

```bash
dart pub global activate fvm   # if not installed
fvm install
```

---

#### Step 2 — Clone & Prerequisites

```bash
git clone https://github.com/Kodi-Entwicklergemeinschaft/kodi-mobile-template-C.git
cd kodi-mobile-template-C
```

| Requirement | Notes |
|---|---|
| [Flutter SDK](https://flutter.dev/docs/get-started/install) | `3.32.0` (managed via FVM) |
| Dart SDK | Bundled with Flutter |
| [Android Studio](https://developer.android.com/studio) / [VS Code](https://code.visualstudio.com/) | With Flutter & Dart plugins |
| Xcode *(iOS only)* | Required for iOS builds |

---

#### Step 3 — Firebase Setup

Create a project in the [Firebase Console](https://console.firebase.google.com), then provide these **gitignored** files:

| File | Location |
|---|---|
| `google-services.json` | `android/app/src/google-services.json` |
| `GoogleService-Info.plist` | `ios/Runner/GoogleService-Info.plist` |
| `firebase_options.dart` | `lib/firebase_option/firebase_options.dart` |

Generate `firebase_options.dart` with the [FlutterFire CLI](https://firebase.google.com/docs/flutter/setup) (`flutterfire configure`).

---

#### Step 4 — Environment (`.envKusel`)

Create a `.envKusel` file in the project root (also gitignored):

```
BASE_URL_PROD=<production_api_base_url>
BASE_URL_STAGE=<staging_api_base_url>
IMAGE_DOWNLOADING_ENDPOINT=<image_storage_base_url>
```

Both flavors load `.envKusel` at bootstrap (`dotenv.load`); the entry point selects which base URL is used.

---

#### Step 5 — Install Dependencies

```bash
fvm flutter pub get
```

---

### ▶️ Running the App

| Flavor | Entry Point | Command |
|---|---|---|
| Staging | `lib/main_dev.dart` | `fvm flutter run --target lib/main_dev.dart` |
| Production | `lib/main_prod.dart` | `fvm flutter run --target lib/main_prod.dart` |

---

### 📦 Release Builds

```bash
# Android App Bundle (Play Store)
fvm flutter build appbundle --target lib/main_prod.dart --release

# Android APK
fvm flutter build apk --target lib/main_prod.dart --release

# iOS (archive via Xcode after this step)
fvm flutter build ios --target lib/main_prod.dart --release
```

> Release signing reads `android/key.properties` (gitignored). Create it with your keystore credentials before a production build.

---

### 📁 Files You Must Provide

These are gitignored and must be added manually:

| File | Description |
|---|---|
| `android/app/src/google-services.json` | Firebase — Android |
| `ios/Runner/GoogleService-Info.plist` | Firebase — iOS |
| `lib/firebase_option/firebase_options.dart` | FlutterFire options |
| `.envKusel` | API + image base URLs |
| `android/key.properties` | Release signing credentials |

---

### ♻️ Code Generation

Run whenever you modify Hive models or annotated classes:

```bash
fvm flutter pub run build_runner build --delete-conflicting-outputs
```

---

### 🤝 Contributing

Contributions are welcome! Feel free to:

- 🍴 Fork this repository
- 🐛 Open an issue to report a bug
- 💡 Submit a pull request with improvements

Please follow the existing code style and patterns used throughout the project.

---

### 📄 License

This project is licensed under the **European Union Public Licence v1.2 (EUPL-1.2)**.
See the [LICENSE](LICENSE) file for details.

---

<br/>

## 🇩🇪 Deutsch

### Was ist Kusel?

**Kusel** ist eine Flutter-basierte mobile Anwendung für den Landkreis Kusel. Sie vereint lokales Gemeinschaftsleben, Tourismus, Mobilität und Bürgerbeteiligung in einer App — Veranstaltungen, Orte, kommunale Dienste und Beteiligung, mit Offline-Unterstützung und einer interaktiven Karte.

---

### ✨ Funktionen

| Funktion | Beschreibung |
|---|---|
| 🗓️ **Veranstaltungen & Kalender** | Lokale Veranstaltungen, Angebote und Highlights nach Kategorie |
| 🧭 **Tourismus & Entdecken** | Sehenswürdigkeiten ("Mein Ort"), Tourismusinhalte und Highlights |
| 🚌 **Mobilität** | Lokale Mobilitätsinformationen und -dienste |
| 🏛️ **Virtuelles Rathaus** | Digitale kommunale Dienste und Ratsinformationen |
| 🗳️ **Bürgerbeteiligung** | Beteiligungs-Flows — Feedback, Vorschläge und Parteiinformationen |
| 🗺️ **Interaktive Karte** | OpenStreetMap-Standortsuche, -auswahl und Kompassnavigation |
| 🏘️ **Mehrere Kommunen** | Kommunen und Städte im Landkreis durchsuchen und favorisieren |
| 📷 **QR-Scanner** | QR-/Barcode-Scan in der App |
| 🎬 **Medien** | Bildergalerien und Videowiedergabe in der App |
| 📴 **Offline-Modus** | Hive-Cache + Offline-Routing ohne Netzwerk |
| 🌐 **Lokalisierung** | Mehrsprachige Oberfläche mit In-App-Übersetzung |

---

### 🚀 Erste Schritte

> **Hinweis:** Mehrere Konfigurationsdateien sind aus Sicherheitsgründen **nicht im Repository enthalten**.
> Folgen Sie allen nachstehenden Schritten, bevor Sie die App starten.

1. **FVM** installieren und `fvm install` ausführen (Flutter `3.32.0`).
2. **Firebase-Dateien** bereitstellen — `google-services.json`, `GoogleService-Info.plist`, `lib/firebase_option/firebase_options.dart`.
3. **`.envKusel`** im Projektstamm anlegen (`BASE_URL_PROD`, `BASE_URL_STAGE`, `IMAGE_DOWNLOADING_ENDPOINT`).
4. Abhängigkeiten installieren: `fvm flutter pub get`.
5. App starten:

```bash
# Staging
fvm flutter run --target lib/main_dev.dart

# Produktion
fvm flutter run --target lib/main_prod.dart
```

Dateinamen und Pfade sind identisch mit der englischen Sektion oben.

---

### ♻️ Code-Generierung

Immer wenn Hive-Modelle oder annotierte Klassen geändert werden:

```bash
fvm flutter pub run build_runner build --delete-conflicting-outputs
```

---

### 🤝 Beitragen

Wir freuen uns über Beiträge aus der Community! Gerne:

- 🍴 Repository forken
- 🐛 Issues melden
- 💡 Pull Requests einreichen

---

### 📄 Lizenz

Dieses Projekt ist unter der **European Union Public Licence v1.2 (EUPL-1.2)** lizenziert.
Details finden Sie in der [LICENSE](LICENSE)-Datei.

---

<div align="center">

Made with ❤️ using [Flutter](https://flutter.dev)

</div>
