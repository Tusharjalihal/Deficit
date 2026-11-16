# Deficit Coach (Android)

Native Android wrapper around the Deficit Coach web app. No account, no internet needed
(internet is used only for the nicer fonts and the exercise demo links).

## Get the APK (about 5 minutes, all from a phone or PC browser)

1. On GitHub, create a new **private** repository, for example `deficit-coach-android`.
2. Upload everything in this folder, **including the hidden `.github` folder**
   (on a PC: drag the folder contents into "Add file > Upload files"; or use `git push`).
3. Open the repo's **Actions** tab. The "Build APK" workflow starts by itself
   (or press "Run workflow"). It takes about 3 to 5 minutes.
4. When it's green, open **Releases** (right side of the repo page) and download
   `DeficitCoach-v1.0.N.apk`. Send that file to your friend on WhatsApp, Drive, etc.

## Installing on your friend's phone

1. Tap the APK. Android asks to allow installs from that app (WhatsApp, Files, Chrome): allow it.
2. If Play Protect says "unknown app", tap **More details > Install anyway**. That's normal for
   apps not from the Play Store.

## Updating later

Edit `app/src/main/assets/index.html`, push. A new release appears with a higher version
number and installs over the old one **without losing data** (same signing key each build).

## Where data lives

In the app's own storage on the phone. It survives updates and restarts. It is erased by
uninstalling or by Settings > Apps > Deficit Coach > Clear storage. The app also has
**Profile > Save backup file** and **Restore from backup**, and Android's own Google backup
includes the app's data.

## Notes

- Signing: the workflow reads a permanent key from the repo secret `KEYSTORE_BASE64`
  (Settings > Secrets and variables > Actions). Without it, builds use a throwaway
  key and are labelled "test": fine for trying the app, but later builds won't
  install over them. The key is never committed, because this repo is public.
- Package name: `in.deficitcoach.app`, minimum Android 7.0, target Android 14.
