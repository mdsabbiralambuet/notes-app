# Notes App — Complete Android Project

A working notes app built with Kotlin + Jetpack Compose (Material 3).
Features: add, edit, delete notes with persistent storage.

## What's included
- `app/src/main/java/com/example/notesapp/MainActivity.kt` — all app code (UI, logic, storage)
- `app/src/main/AndroidManifest.xml` — app manifest
- `app/build.gradle` — app dependencies (Compose, Material 3)
- `build.gradle`, `settings.gradle`, `gradle.properties` — project config

## Execution plan — what YOU do

### Step 1: Install Android Studio
Download from https://developer.android.com/studio (free, ~1 GB).
Install with default options. On first launch it will download the Android SDK (~3 GB more).

### Step 2: Open the project
1. Unzip the project folder somewhere (e.g. `C:\AndroidProjects\NotesApp`).
2. In Android Studio: **File → Open** → select the `NotesApp` folder.
3. It will say "Gradle sync" at the bottom — wait ~2–5 minutes the first time.
   It downloads dependencies. **You need internet for this step.**

### Step 3: Set up a device to run on
Pick ONE:

**Option A — Emulator (recommended for first try)**
1. Top toolbar → **Device Manager** icon (looks like a phone+).
2. Click **Create Virtual Device** → pick "Pixel 7" → Next.
3. Pick a system image (any API 33+/Android 13+). Click Download next to it, then Next → Finish.
4. The virtual device now appears in the dropdown next to the green ▶ Run button.

**Option B — Real Android phone**
1. On your phone: Settings → About phone → tap "Build number" 7 times to enable Developer Options.
2. Settings → Developer options → enable **USB debugging**.
3. Plug phone into PC via USB. Accept the "Allow debugging?" prompt on the phone.
4. The phone appears in the device dropdown in Android Studio.

### Step 4: Run it
Press the green ▶ Run button (or Shift+F10).
First build takes 1–3 minutes. After that, the app launches automatically.

### Step 5: Use it
- Tap the **+** button to add a note.
- Tap **Edit** or **Delete** on any note card.
- Close and reopen — your notes persist (saved to device storage).

## Troubleshooting

| Problem | Fix |
|---|---|
| Gradle sync fails | Check internet. **File → Invalidate Caches → Invalidate and Restart**. |
| "SDK not found" | **Tools → SDK Manager** → install Android 14 (API 34) platform. |
| Emulator slow/won't start | Enable hardware virtualization in BIOS (Intel VT-x or AMD-V). |
| "Unresolved reference: compose" | Wait for Gradle sync to finish (bottom status bar). |
| Phone not detected | Try a different USB cable; install your phone manufacturer's USB driver on Windows. |

## How to extend it
- Replace SharedPreferences with **Room** (SQLite) for a real database.
- Add note search with a TextField at the top.
- Add categories/tags as a second data field.
- Sync to cloud with Firebase Firestore.
- Add a dark theme toggle (Material 3 already supports it — switch `lightColorScheme()` to `darkColorScheme()`).

## What's happening in the code (quick tour)
- **`Note` data class** — one note = id + title + body + timestamp.
- **`NoteStorage`** — saves/loads the notes list as JSON in SharedPreferences (a tiny key-value store every Android app gets for free).
- **`MainActivity`** — entry point; sets up the Compose UI.
- **`NotesApp`** — top-level screen: list + floating action button + editor dialog.
- **`NoteCard`** — one note row with Edit/Delete buttons.
- **`NoteEditorDialog`** — the popup for creating or editing a note.

All UI is declarative (Jetpack Compose) — you describe what the screen looks like for a given state, and Compose redraws when the state changes.
