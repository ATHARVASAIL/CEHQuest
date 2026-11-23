# CEH Quest - Android project

The CEH Quest study app wrapped as a native Android app (works fully offline).

## Option A: let GitHub build the APK (no install, ~5 minutes)
1. On github.com create a new **private** repository (for example `cehquest`).
2. Unzip this project on your computer, then on the repo page use **Add file > Upload files** and drag in
   everything inside the `CEHQuest` folder (including the hidden `.github` folder). Commit.
   If `.github` did not upload: open the **Actions** tab > **set up a workflow yourself**, paste the
   contents of `.github/workflows/build-apk.yml`, and commit.
3. Open the **Actions** tab. The "Build APK" run starts automatically and takes about 4 minutes.
4. Open the finished run, download **CEHQuest-apk** under Artifacts, unzip it, and copy `app-debug.apk` to your phone.
5. Open the APK on the phone and allow "Install unknown apps" when Android asks.

## Option B: build with Android Studio (about 5 minutes)
1. Install Android Studio (free): https://developer.android.com/studio
2. File > Open > choose this `CEHQuest` folder. Let Gradle sync finish (it downloads the build tools once).
3. Build > Build App Bundle(s) / APK(s) > Build APK(s).
4. Click "locate" in the popup. Copy `app-debug.apk` to your phone and open it
   (allow "Install unknown apps" for your file manager when Android asks).

Or plug your phone in with USB debugging on and press the green Run button.

Command line alternative (needs JDK 17, Gradle 8.7+ and the Android SDK): run `gradle wrapper` once, then `./gradlew assembleDebug`
The APK appears in `app/build/outputs/apk/debug/`.

## Notes
- Progress is stored on the phone. Use Me > Export progress code to back it up or move it
  to the web version, and Import progress code to bring it back.
- Cloud sync and the "Explain it differently" button need the claude.ai version of the app;
  they are hidden in the offline APK.
