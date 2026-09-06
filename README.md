# WeekNote

A paper-notebook style weekly planner. Wraps a single `weeknote.html`
into an Android app via Capacitor + AdMob.

## Build & run

```bash
git clone https://github.com/vladuniversal1611-arch/weeknote.git
cd weeknote
npm install         # installs deps, builds www/, adds Android, patches manifest
npm run android     # opens the project in Android Studio → click ▶ Run
```

## After editing `weeknote.html`

```bash
npm run sync        # rebuild www/ and sync into the native Android project
```

## Files

| Path | What |
|------|------|
| `weeknote.html` | The whole app (Light + Pro modes, 19 languages, themes, calendar, stats, notes) |
| `assets/` | Notebook sprites — leather, paper, brass discs, corner curl, desk background |
| `package.json` | npm scripts + Capacitor / AdMob dependencies |
| `capacitor.config.json` | Capacitor config with AdMob app ID |
| `scripts/build-www.js` | Wraps `weeknote.html` in an HTML shell and copies it to `www/` |
| `scripts/setup-android.js` | Runs `cap add android`, `cap sync`, patches AndroidManifest with AdMob APPLICATION_ID |

## AdMob

IDs are hard-coded in `weeknote.html` (`ADMOB` const). The device you
develop on should be registered as a test device in the AdMob console —
Google will then serve test creatives against your real ad unit IDs.
