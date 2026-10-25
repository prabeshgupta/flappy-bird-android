# Flappy Bird (Modern Android Edition) 🐦

An authentic recreation of the legendary 2013 Flappy Bird, rebuilt for **modern 64-bit Android devices (Android 14, 15, 16+)**. 

The original 2013 32-bit Flappy Bird binaries can no longer be installed or run on modern Android operating systems. This project brings back the nostalgic gameplay experience with native 64-bit ARM support, instant startup (no splash screen delay), a clean home screen, and an in-game retro settings menu to customize your bird, world themes, and physics.

---

## 🎮 Gameplay Preview

| Get Ready | In-Flight Flapping | Game Over Screen |
| :---: | :---: | :---: |
| <img src="public/Screenshot_20261026-031430.jpg" width="220" /> | <img src="public/Screenshot_20261026-031508.jpg" width="220" /> | <img src="public/Screenshot_20261026-031513.jpg" width="220" /> |

🎬 **Gameplay Video Recording:** Watch the full screen recording in [`public/Screen_Recording_20261026_030443.mp4`](public/Screen_Recording_20261026_030443.mp4).

---

## 📥 For Gamers: Download & Play

No need to compile anything if you just want to play! Grab the ready-to-install APK:

👉 **[Download FlappyBird.apk](FlappyBird.apk)** *(~7.9 MB, Pre-signed and tested)*

You can also download it from the [Releases](https://github.com/prabeshgupta/flappy-bird-android/releases) section.

### Quick Install Steps:
1. Download **[FlappyBird.apk](FlappyBird.apk)** to your Android device.
2. Open your device's **Files** or **Downloads** app and tap the APK.
3. If prompted, allow **"Install unknown apps"** for your file manager.
4. Tap **Install** and you're ready to flap!

---

## ⚙️ In-Game Settings & Customization

Tap the handcrafted retro pixel-art gear icon in the top-right corner anytime—accessible from both the **Home Screen** and the **Game Over Screen**:

| Bird & Themes | Physics Sliders | Toggles & Haptics |
| :---: | :---: | :---: |
| <img src="public/Screenshot_20261026-031517.jpg" width="220" /> | <img src="public/Screenshot_20261026-031527.jpg" width="220" /> | <img src="public/Screenshot_20261026-031530.jpg" width="220" /> |

### Features you can toggle & tune:
- **Bird Skins:** Classic Yellow, Red, Blue, or animated Rainbow bird.
- **World Themes:** Day or Night background, pipe colors (Green, Red, Blue, Yellow).
- **Physics Sliders:** Adjust game speed, gravity, jump impulse, pipe gap size, and bird hitbox size (great for training or casual play).
- **Special Modes:** Moving pipes, pipe variation tiers, reverse pipes, ghost mode, and infinite flap.
- **Haptic & Sound:** Toggle wing flap vibration feedback and retro sound effects. Reset everything back to vanilla with one tap.

---

## 🛠️ For Developers: Source Code & Building

This repository is a standard **Android Studio / Gradle** project with full Java source code.

### Project Layout:
```
FlappyBird/
├── FlappyBird.apk            # Prebuilt, tested & signed working release APK
├── build.gradle              # Top-level Gradle build configuration
├── settings.gradle           # Project module settings
├── app/
│   ├── build.gradle          # App build configuration (SDK 35, dependencies)
│   └── src/main/
│       ├── AndroidManifest.xml
│       ├── java/com/flappybird/recreation/
│       │   ├── MainActivity.java      # Main game loop, Canvas rendering & input
│       │   ├── SettingsActivity.java  # Settings screen & SharedPreferences
│       │   ├── GearslogoActivity.java # Instant launch splash bypass
│       │   └── FlappyClassy.java      # Application base class
│       └── res/              # Game audio (raw/), sprites (drawable/), and layouts
├── public/                   # Gameplay screenshots and full gameplay screen recording
├── .gitattributes            # Git LFS configuration for video tracking
├── .gitignore                # Android & IDE build ignore rules
└── README.md
```

### Building in Android Studio:
1. Clone this repository:
   ```bash
   git clone https://github.com/prabeshgupta/flappy-bird-android.git
   cd flappy-bird-android
   ```
2. Open Android Studio and choose **Open an Existing Project**, selecting this root folder.
3. Let Gradle sync dependencies (requires Java 17+).
4. Run on your connected Android device or emulator with **Run > Run 'app'** (`Shift + F10`).

### Building via Command Line:
```bash
# Build a debug APK
./gradlew assembleDebug

# Build a release APK
./gradlew assembleRelease
```
The output APK will be generated under `app/build/outputs/apk/`.

---

## 🔍 Technical & Compatibility Fixes

1. **64-bit & Modern Android OS Support:**
   - Compiled with `targetSdkVersion 35` and `minSdkVersion 21`.
   - Native 64-bit (`arm64-v8a`) architecture compliance prevents modern Android warnings.
2. **Instant Launch Bypass:**
   - `GearslogoActivity` immediately transitions into `MainActivity` without delays.
3. **Clean Home UI:**
   - Centered classic Play button.
   - Removed non-functional `123` scorecard placeholder button.
   - Removed obsolete bottom copyright text.
4. **Bytecode / Verifier Fixes:**
   - Fixed a Dalvik/ART type-verification crash (`VerifyError`) in `SettingsActivity` when invoking haptic feedback.
   - Fixed the settings button disappearing on the Game Over screen by anchoring its position directly to `systemBarTop + margin`.
   - Added null-checks for frame restart dimension queries.

---

## 📜 Credits & Disclaimer

Original Flappy Bird game design and assets by **Dong Nguyen / dotGEARS (2013)**. This repository is an educational preservation and modern compatibility project.
