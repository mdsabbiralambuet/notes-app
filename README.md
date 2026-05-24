# 📝 Notes App

A clean, minimal notes app for Android — my **first Android app**, built with Kotlin and Jetpack Compose.

Add notes, edit them, delete them. Everything saves automatically and persists between launches. No accounts, no ads, no internet required.

---

## ✨ Features

- ✏️ Create, edit, and delete notes
- 💾 Auto-save to local storage (notes survive app restarts)
- 🎨 Material Design 3 styling
- 📱 Works on any Android 7.0+ device (API 24+)
- 🔌 Fully offline — no permissions, no tracking, no internet

## 📸 Screenshots

> _Coming soon — add your screenshots here._

<!--
To add screenshots later:
1. Run the app, take screenshots from your phone or emulator.
2. Save them in a `screenshots/` folder in this repo.
3. Replace this block with:
   ![Empty state](screenshots/empty.png)
   ![Note list](screenshots/list.png)
   ![Editor](screenshots/editor.png)
-->

## 🛠 Built with

- **Kotlin** — the language
- **Jetpack Compose** — declarative UI toolkit
- **Material 3** — modern design system
- **SharedPreferences** — lightweight local storage (notes serialized as JSON)

## 🚀 Try it

### Install the prebuilt APK
1. Download the latest `app-debug.apk` from the [Releases](../../releases) page.
2. On your Android device, open the APK and tap **Install**.
   You may need to enable "Install from unknown sources" the first time.
3. Open the app and start writing.

### Or build it yourself
1. Clone the repo:
   ```bash
   git clone https://github.com/mdsabbiralambuet/notes-app.git
   ```
2. Open the project in **Android Studio** (Hedgehog or newer).
3. Let Gradle sync finish.
4. Press ▶ Run.

Minimum requirements: Android Studio with SDK 34, JDK 17.

## 📂 Project structure

```
app/src/main/
├── java/com/example/notesapp/
│   └── MainActivity.kt          # All app logic in a single file
├── res/                         # Resources
└── AndroidManifest.xml          # App manifest
```

The entire app lives in **one Kotlin file** (`MainActivity.kt`), kept simple and readable on purpose:

- `Note` — data class for each note (id, title, body, timestamp)
- `NoteStorage` — load/save notes as JSON in SharedPreferences
- `NotesApp` — top-level Composable: list + floating action button
- `NoteCard` — individual note in the list, with edit/delete actions
- `NoteEditorDialog` — modal for creating or editing notes

## 💡 Ideas for v2

Things I might add next:

- [ ] Search bar to filter notes
- [ ] Categories or tags
- [ ] Dark theme toggle
- [ ] Export notes as text or PDF
- [ ] Migrate from SharedPreferences to Room (SQLite) for handling many notes
- [ ] Optional cloud sync

## 🙏 About

This was my first Android app — a starting point for learning Kotlin, Jetpack Compose, and the Android build pipeline. The code is intentionally compact and beginner-friendly, all in one file, so other beginners can read it end to end.

## 📄 License

MIT — feel free to use, modify, or learn from this code.
