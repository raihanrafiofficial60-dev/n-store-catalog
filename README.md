# n-store-catalog

Official public application catalogue for **N Store** — featuring **N Studio Originals** (`N Chord`, `N Stream`, `N Flix`, `N EMMX`, `Screen X`, `XScamera`).

## Repository Structure

```text
n-store-catalog/
├── catalog/
│   └── apps.json                  # Centralized JSON catalogue (Official N Studio + future Community section)
├── assets/
│   ├── logo/
│   │   └── n-store-logo.png       # Official N Store logo
│   └── apps/
│       ├── n-chord/               # Icon + 12 official screenshots
│       ├── n-stream/              # Icon + 9 official screenshots
│       ├── n-flix/                # Icon + 6 official screenshots
│       ├── n-emmx/                # Icon + 4 official screenshots
│       ├── screen-x/              # Ready for Screen X assets
│       └── xscamera/              # Ready for XScamera assets
└── README.md
```

## Publishing to GitHub & Enabling Direct APK Downloads

1. Create a **public** GitHub repository named `n-store-catalog` under your GitHub account.
2. Push this `n-store-catalog` folder to `main`:
   ```bash
   cd "d:/MY APPS/N Store/n-store-catalog"
   git init
   git add .
   git commit -m "Initial N Store official catalogue"
   git branch -M main
   git remote add origin https://github.com/<YOUR_USERNAME>/n-store-catalog.git
   git push -u origin main
   ```
3. Upload your APK binaries to **GitHub Releases** (e.g. tag `v1.9` with `N-Chord.apk`, `v0.5.7` with `N-Stream-v0.5.7-build125-universal-release.apk`, `v2.3.1` with `N-Flix-v2.3.1.apk`, `v0.5.114` with `N-EMMX-v0.5.114.apk`).
4. Update each app's `downloadUrl` and set `"status": "published"` in `catalog/apps.json`:
   ```json
   "downloadUrl": "https://github.com/<YOUR_USERNAME>/n-store-catalog/releases/download/v2.3.1/N-Flix-v2.3.1.apk",
   "status": "published"
   ```
5. In the N Store Android app (`app/build.gradle.kts`), set `DEFAULT_CATALOG_OWNER` to `<YOUR_USERNAME>`. N Store automatically fetches `https://raw.githubusercontent.com/<YOUR_USERNAME>/n-store-catalog/main/catalog/apps.json` and caches it locally!
