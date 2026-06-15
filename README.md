# Booked & Planned — Book Tracker (PWA)

A personal book tracker / planner with a books gallery, PDF library, dashboard,
and "Year in Books" stats. Works as an installable app (PWA) on phone and laptop.

## Files

- `index.html` – the app itself
- `manifest.json` – PWA manifest (name, icons, colors)
- `sw.js` – service worker (offline support)
- `icon.svg`, `icon-192.png`, `icon-512.png` – app icons

All four files must stay in the **same folder**, and `index.html` must be opened
from the same URL/path every time (don't move it around) so your books and PDFs
stay in place.

## Hosting for free (GitHub Pages)

1. Create a free GitHub account at github.com if you don't have one.
2. Create a new repository (e.g. `booked-and-planned`), public.
3. Upload all 5 files (`index.html`, `manifest.json`, `sw.js`, `icon.svg`,
   `icon-192.png`, `icon-512.png`) to the repository root — drag and drop on
   the GitHub website works fine.
4. Go to the repo's **Settings → Pages**.
5. Under "Source", choose the branch (usually `main`) and folder `/ (root)`,
   then save.
6. After a minute, GitHub gives you a URL like:
   `https://yourusername.github.io/booked-and-planned/`
7. Open that URL on your laptop and your phone.

## Installing on your phone

- **Android (Chrome)**: open the URL → menu (⋮) → "Add to Home screen" / "Install app".
- **iPhone (Safari)**: open the URL → Share icon → "Add to Home Screen".

This adds an app icon that opens full-screen, works offline once loaded, and
keeps its own data on that device.

## Moving your library between devices

Each device (laptop browser, phone app) stores its books and PDFs separately —
there's no automatic sync. Use the in-app **Backup & Restore** page:

1. On the device with your data: go to **Backup & Restore → Download Backup File**.
   This saves a `.json` file containing all your books and attached PDFs.
2. Send that file to your other device (email, cloud drive, USB, etc.).
3. On the other device: go to **Backup & Restore → Import Backup**, choose the
   file. This replaces that device's library with the one from the backup.

Do this any time you want to bring your laptop library to your phone (or vice versa).
Keep a backup file saved somewhere safe as well, in case you ever clear browser data.

## Why books "disappeared" when moving the file locally

Browsers store data per file location when you open HTML files directly
(`file://...`). Moving `index.html` to a different folder, or opening it from
a different path, can make the browser treat it as a different app with empty
storage. Hosting it on a real `https://` URL (step above) fixes this permanently —
the URL never changes even if you update the files.
