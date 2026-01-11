# Ravi's Logic Vault — Capacitor Mobile Wrapper

This project wraps the existing quiz web app into a Capacitor mobile app. It uses the `www/` folder as the web runtime (your provided HTML/CSS/JS).

Quick setup (local machine)
1. Install Node.js (16+ recommended) and npm.
2. Clone or copy this project locally and cd into its folder.
3. Install dependencies:
   ```bash
   npm install
   ```
4. (Optional) Serve the web app locally for quick iteration:
   ```bash
   npm run start
   # open http://localhost:8080 in your browser
   ```

Initialize Capacitor and add platforms
1. Initialize Capacitor (if not already initialized):
   ```bash
   npx cap init "Ravi's Logic Vault" com.ravisuryavanshi.iqvault --web-dir=www
   ```
   Note: If you already have `capacitor.config.json`, skip specifying --web-dir.

2. Add Android:
   ```bash
   npx cap add android
   ```
   Then open Android Studio:
   ```bash
   npx cap open android
   ```

3. Add iOS (macOS only):
   ```bash
   npx cap add ios
   ```
   Open Xcode:
   ```bash
   npx cap open ios
   ```

Build/update the web assets and copy to native projects
- After editing files in `www/`, copy the latest web assets into native projects:
  ```bash
  npx cap copy
  npx cap sync
  ```

Notes
- High score persistence uses localStorage (works in the WebView). If you want native persistent storage, we can add the Capacitor Storage plugin later.
- App id used: `com.ravisuryavanshi.iqvault`. Change it in `capacitor.config.json` before adding platforms if you prefer something else.
- Provide an app icon and splash images (place them under `android/app/src/main/res/` or use Capacitor community plugins to generate icons automatically).

If you want, I can:
- Add Capacitor Storage plugin for a native API.
- Generate placeholder app icons and splash screens.
- Add simple analytics or share/feedback features.

Enjoy! Run the commands above to open the native projects and test on device/emulator.