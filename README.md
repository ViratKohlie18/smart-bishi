# Smart Bishi Android APK

This repository packages the Smart Bishi HTML app inside an Android app using Capacitor. GitHub Actions builds a debug APK.

## Repository layout

The repository root must contain `package.json`, `capacitor.config.json`, `www/`, and `.github/`.

## Build on GitHub

1. Create a **Public** GitHub repository named `smart-bishi`.
2. Upload the *contents* of this folder, not the outer folder itself. Make sure `.github/workflows/build-apk.yml` is included.
3. Open **Actions**. If prompted, enable workflows.
4. Choose **Build APK** and select **Run workflow**, or push/commit to `main`.
5. Open the completed run and download the `smart-bishi-apk` artifact.
6. Extract `app-debug.apk` from the downloaded artifact ZIP and install it on your Android phone.

## Data and backups

The app stores records in device-local browser storage. Use the in-app **Export Backup** button before uninstalling or replacing the app, and keep the JSON backup somewhere safe. Importing a backup replaces the current records on that device.

## Important

- This workflow creates a debug APK for testing, not a Play Store release.
- A fresh GitHub build uses a new debug signing key. To install an updated build over an existing installation, you need a stable release-signing setup. Without it, uninstalling the old app may be required, which deletes its local data.
- Keep exported JSON backups before updates or reinstallations.
