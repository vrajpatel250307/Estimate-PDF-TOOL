# Estimate PDF Tool

Create clean, print-ready estimates from a live A4 preview and export them as PDFs. The web editor supports Gujarati and English text, adjustable text size, and flexible writing space. An optional native Android app saves estimates on the device.

> This public edition does not include a server-side database or SQL connection. The web editor does not upload estimate content. The Android app stores records locally on the device.

## Features

- Live A4 portrait preview over the supplied letterhead
- Gujarati and English text entry
- Adjustable font size and writing space
- PDF export from the browser
- Responsive editor for desktop and mobile
- Native Android app with local estimate history and PDF export
- No website database, SQL server, or account required

## Web app

### Run locally

The editor is a PHP page with no PHP backend dependencies. Serve the project directory using XAMPP/Apache or PHP's built-in server:

```bash
php -S localhost:8000
```

Then open [http://localhost:8000](http://localhost:8000).

The PDF libraries and web fonts load from public CDNs, so an internet connection is required for those resources. Estimate data stays in the current page and is not saved to a server.

### Use it

1. Enter a customer or organization name.
2. Add work details in Gujarati or English.
3. Adjust text size and writing space to fit the letterhead.
4. Enter the total cost.
5. Select **Export PDF** to download the estimate.

## Android app

The `native-android/` directory contains a native Android version. It uses the device's Gujarati keyboard, previews estimates on the included letterhead, exports PDFs, and saves estimate history in the app's local SQLite storage.

### Build a debug APK on macOS

1. Install Android Studio and Android SDK Platform 35.
2. Open a terminal in `native-android/` and run:

   ```bash
   ./gradlew assembleDebug
   ```

3. Find the APK at `app/build/outputs/apk/debug/app-debug.apk`.

The wrapper downloads Gradle 8.9 on first use. The project uses Android Gradle Plugin 8.7.3, Kotlin 2.0.21, and Android API 29 as its minimum version.

## Project files

| Path | Purpose |
| --- | --- |
| `index.php` | Web editor and A4 preview markup |
| `app.js` | Browser editor controls and live preview |
| `pdf-export.js` | Browser PDF generation |
| `style.css` | Responsive web app styling |
| `letterhead.pdf` | Letterhead artwork used for PDF output |
| `letterhead.png` | Letterhead artwork used in the live preview |
| `native-android/` | Native Android application |

## Privacy and deployment

This repository intentionally excludes the former PHP/MySQL persistence layer and its connection settings. The web version runs without SQL and does not send entered estimate details to a server. The Android version's SQLite database is local to each device. The supplied letterhead artwork is included as project content; confirm you have permission to redistribute it before republishing this repository or using the artwork commercially.

## License

No license is currently provided. Unless a license is added, standard copyright applies and reuse or redistribution is not automatically permitted. Add an appropriate license if you want to allow others to use or modify the code.
