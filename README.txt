DAILY CARDS — FLAT UPLOAD PACKAGE

Files:
- index.html: complete offline-first web app (HTML/CSS/JS in one file)
- native-bridge.js: Capacitor native save/share bridge, bundled by GitHub Actions
- package.json: Capacitor dependencies
- capacitor.config.json: Android app configuration
- build.yml: paste into .github/workflows/build.yml in GitHub
- sample-data.csv: sample CSV including optional image and audio data URIs
- sample-data.json: sample JSON import

GitHub setup:
1. Create a new GitHub repository.
2. Upload the five project files (not README if you don't want it) to the repository root.
3. Create folders .github/workflows in GitHub's Add file > Create new file flow by naming the file .github/workflows/build.yml.
4. Paste the contents of build.yml into that file and commit.
5. Open Actions, choose Build Daily Cards APK, and run workflow if it did not run on push.
6. Open the successful workflow run, find Artifacts, download daily-cards-debug-apk, and extract app-debug.apk.
7. On Android, open the APK and allow installation from that source if Android asks.

Important:
- The workflow creates www and android during build; do not upload generated folders.
- This workflow creates a debug APK for personal installation, not a Play Store release.
- Browser app data is stored in IndexedDB. Android exports use Capacitor Filesystem + Share when the native plugins are available; otherwise the app uses the browser download fallback.
- Import files with the Import daily file button. CSV headers should use fields such as front,pinyin,meaning,example,example_translation,image,audio,grammar,category,notes.
- Image/audio may be data URIs (best for a self-contained offline CSV) or URLs. URLs may not work offline. When manually adding/editing a card, you can also attach image/audio files directly from the phone.
- Sample audio is a short test tone, not spoken Chinese.
