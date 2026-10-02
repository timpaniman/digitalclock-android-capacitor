# Digital Clock (Android / Capacitor)

A small Android digital clock built with [Capacitor](https://capacitorjs.com/).  
The UI is plain HTML, CSS, and JavaScript — the same style as the desktop Electron / Tauri clocks.

## Requirements

- [Node.js](https://nodejs.org/) 18+
- [Android Studio](https://developer.android.com/studio) with Android SDK
- An Android emulator (for example Pixel 7, API 35) or a USB-connected phone with USB debugging enabled

## Clone and install

```bash
git clone https://github.com/timpaniman/digitalclock-android-capacitor.git
cd digitalclock-android-capacitor
npm install
```

## Run on an emulator or device

1. Start an Android emulator from Android Studio **Device Manager**, or plug in a phone.
2. Sync the web UI into the Android project, then run:

```bash
npx cap sync android
npx cap run android
```

### Or use Android Studio

```bash
npx cap sync android
npx cap open android
```

In Android Studio:

1. Wait for Gradle sync to finish
2. Select your emulator/device in the toolbar
3. Press the green **Run** button

If Android Studio asks for the SDK path, use your local SDK (often `%LOCALAPPDATA%\Android\Sdk` on Windows).

## Modify the UI (HTML / CSS / JS)

Edit this file:

```text
www/index.html
```

That single file contains:

- HTML layout
- CSS (colors, fonts, spacing)
- JavaScript (clock refresh)

Do **not** edit files under `android/app/src/main/assets/public` — Capacitor overwrites them on sync.

### Preview in a browser (optional)

Open `www/index.html` directly in Chrome while you tweak styles.

### Apply changes to Android

After editing `www/index.html`:

```bash
npx cap sync android
```

Then Run again in Android Studio, or:

```bash
cd android
./gradlew installDebug
```

On Windows:

```bat
cd android
gradlew.bat installDebug
```

## Project layout

```text
www/index.html          ← edit the clock UI here
capacitor.config.json   ← app id / name / webDir
android/                ← generated Android Studio project
package.json
```

## Build a debug APK

```bash
npx cap sync android
cd android
./gradlew assembleDebug
```

APK output:

```text
android/app/build/outputs/apk/debug/app-debug.apk
```

## License

MIT
