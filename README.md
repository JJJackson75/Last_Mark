# Last Mark — Game Retrieval App

A field tool for marking your shot location, projecting where the animal likely went down, and tracking blood/sign back to a recovery point. Works as an installable app on your phone (no app store needed).

## What's in this folder

- `index.html` — the entire app (map, GPS, compass, tracking logic)
- `manifest.json` — makes it installable to your home screen
- `sw.js` — lets it work offline once you've opened it with signal at least once
- `icon-192.png` / `icon-512.png` — app icon

## How to put this on your phone

A phone browser won't grant GPS/compass access to a file opened straight off disk — it needs to be served over `https://`. The easiest free options:

### Option A — Netlify Drop (easiest, 2 minutes)
1. Go to **app.netlify.com/drop** in a browser on your computer
2. Drag this whole folder onto the page
3. It gives you a live `https://` link instantly
4. Open that link on your phone

### Option B — GitHub Pages (free, more permanent)
1. Create a new GitHub repository
2. Upload these 5 files to it
3. In the repo's Settings → Pages, enable Pages for the main branch
4. You'll get a `https://yourname.github.io/reponame/` link

### Option C — Any web host you already have
Just upload the 5 files to any folder on a site you control — no server-side code needed, it's all static files.

## Installing it on your phone once it's hosted

**iPhone (Safari):**
1. Open the link
2. Tap the Share icon → **Add to Home Screen**
3. It now opens full-screen with its own icon, just like an app

**Android (Chrome):**
1. Open the link
2. Chrome will usually show an "Install" banner at the bottom — tap it
3. Or tap the **⋮** menu → **Add to Home screen** / **Install app**

## Using it in the field

1. Open the app (allow location access when asked — and on iPhone, you may also get a compass/motion permission prompt)
2. When you take a shot: tap **Mark Shot**, set the distance and direction (drag the compass needle, or tap "Use Phone Heading" to auto-fill your current facing), then confirm
3. A gold pin appears showing the estimated location
4. As you walk in and find blood or sign, tap **Add Sign** each time at that spot — this drops a numbered pin and re-estimates the remaining distance along your original line
5. The bottom panel always shows live distance and bearing to your most recent mark, so you can navigate without staring at the map
6. **Reset** clears everything to start a new hunt

## Notes

- Map tiles come from OpenStreetMap and need a signal to load the *first* time you view an area — after that they're cached for offline use
- GPS accuracy (shown top-right) depends on your phone and sky visibility; open ground gives better fixes than dense cover
- The compass uses your phone's magnetometer — it can drift near vehicles or metal structures, so the manual drag option is there as a backup
