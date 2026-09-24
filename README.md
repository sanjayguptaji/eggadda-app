# Eggadda Android app

"Har anda apne andaz mai" — the Eggadda menu as an Android app. The full menu is bundled in
`app/src/main/assets/index.html`, so it opens offline. "My plate" is remembered between visits and
"Copy order" copies the order to the phone clipboard for WhatsApp.

## Get the APK (pick one)

**A. Android Studio (easiest)**
1. Install Android Studio, then File → Open → this `EggaddaApp` folder.
2. Wait for Gradle sync, then Build → Build App Bundle(s)/APK(s) → Build APK(s).
3. The APK is at `app/build/outputs/apk/debug/app-debug.apk`. Copy it to a phone and install.

**B. GitHub, no install needed**
1. Create a GitHub repository and upload the contents of this folder.
2. The included workflow (`.github/workflows/build-apk.yml`) builds automatically.
3. Open the Actions tab → latest run → download `eggadda-debug-apk`.

## Publishing on Google Play
Build → Generate Signed Bundle/APK → Android App Bundle, create an upload key, and upload the `.aab`
in Play Console. Package name: `com.eggadda.app` (change it in `app/build.gradle.kts` before first upload if you want another).

## Changing the menu
Edit `app/src/main/assets/index.html` (the MENU list near the bottom holds every dish). Prices, address,
phone and Instagram are placeholders in the menu PDF — fill them there.
To load the live website instead of the bundled copy once eggadda.com is hosted, set
`START_URL = "https://eggadda.com"` in `MainActivity.kt`.
