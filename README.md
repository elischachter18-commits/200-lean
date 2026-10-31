# 200 Lean

A full-screen workout and weigh-in tracker for iPhone, synced with Firebase and hosted on GitHub Pages.

## Files

| File | What it is |
|---|---|
| `index.html` | The app |
| `firebase-config.js` | Your Firebase project's web config (fill this in) |
| `manifest.webmanifest`, `icon-*.png`, `apple-touch-icon.png` | Home-screen app name and icons |
| `sw.js` | Lets the app open with no signal |
| `firestore.rules` | Security rules to paste into Firebase (not used by the site itself) |

## Setup

### 1. Firebase (sync)
1. Go to console.firebase.google.com and create a project named `200-lean`. Google Analytics is not needed.
2. **Build > Authentication > Get started > Email/Password**: turn on the first switch and save.
3. **Build > Firestore Database > Create database**: choose a location near you, start in **production mode**.
4. In Firestore, open the **Rules** tab, replace everything with the contents of `firestore.rules`, and publish.
5. **Project settings (gear) > Your apps > Web (`</>`)**: register an app named `200 Lean` (no hosting). Copy the `firebaseConfig` values into `firebase-config.js`.

### 2. GitHub Pages (hosting)
1. Create a free account at github.com.
2. New repository named `200-lean`, **Public**.
3. **Add file > Upload files**: drag in every file from this folder and commit.
4. **Settings > Pages**: Source **Deploy from a branch**, branch **main**, folder **/ (root)**, save.
5. After a minute or two the app is live at `https://<your-username>.github.io/200-lean/`.

In Firebase, **Authentication > Settings > Authorized domains**, add `<your-username>.github.io`.

### 3. On your iPhone
1. Open the address in **Safari** and tap **Share > Add to Home Screen**.
2. Open it from the home-screen icon and **Create account** with your email and a password.
3. On your laptop, open the same address, sign in, go to **Goals > Import backup**, and pick `200-lean-backup-2026-10-30.json`. It syncs to your phone.

Once your own account exists, you can stop anyone else signing up: **Authentication > Settings > User actions**, untick **Enable create (sign-up)**.

## Updating
Upload the changed files to the same repository. The app picks up the new version the second time you open it.
