# Kavin's Solids

A home-screen web app for Kavin's first 12 weeks of solids (7 Nov 2026 to 7 Feb 2027): daily plan, allergen schedule, food prep guide, meal log with GP report, and a printable fridge safety sheet. Breast milk stays his main food throughout.

## Files

| File | What it is |
|---|---|
| `index.html` | The app |
| `plan-data.js` | All the plan content (meals, allergens, foods, tips). Edit this to change the plan |
| `fridge.html` | Printable one-page safety sheet (also linked from the Safety tab) |
| `Kavin-fridge-safety-sheet.pdf` | The same sheet as an A4 PDF, ready to print |
| `sw.js`, `manifest.webmanifest`, `icons/` | Make it work offline and install like an app |

## 1. Put it on GitHub Pages (about 5 minutes)

1. On github.com, create a new repository, for example `kavin-solids`. It can be **public or private**, but GitHub Pages on a private repo needs a paid plan. A public repo is fine: no personal data is stored in these files. Your log lives in a private gist (step 3), not in the repo.
2. Upload every file and the `icons` folder (Add file → Upload files, drag the whole folder in, Commit).
3. Settings → Pages → Source: **Deploy from a branch**, Branch: `main`, folder `/ (root)` → Save.
4. After a minute your app is live at `https://ranjitheiv.github.io/solid-starts/`.

## 2. Add it to both iPhones

1. Open the link in **Safari** (not Chrome).
2. Tap Share → **Add to Home Screen** → Add.
3. Open it from the home-screen icon. It runs full-screen and works offline.

## 3. Turn on sync between your phones (about 10 minutes, once)

1. GitHub → Settings → Developer settings → Personal access tokens → **Fine-grained tokens** → Generate new token.
2. Name: `Kavin solids`. Expiration: 1 year (or longer). Repository access: leave as is. Under **Account permissions**, set **Gists** to **Read and write**. Nothing else. Generate, then copy the token.
3. On **Aranei's phone**: open the app, tap the sync button (top right), paste the token, leave Gist ID blank, tap **Connect**. The app creates a private gist and syncs.
4. Tap **Copy Gist ID for the other phone**. AirDrop the Gist ID and the token to RT.
5. On **RT's phone**: open the app, tap sync, choose RT, paste the token and Gist ID, tap **Connect**.

The dot on the sync button is green when synced, orange while syncing, red if there's a problem. The app syncs when it opens, after every change and every minute while it's open. If you're offline, changes stay on the phone and sync next time.

The token can only read and write gists on your account. It's stored only on each phone and never put in the gist. If you lose a phone, delete the token on GitHub and make a new one.

## Day to day

- **Today**: what to offer, with the new allergen steps when it's an allergen day. Tap the circle when he's eaten it. Tap **Edit** to record how much and any reaction.
- **Plan**: every week with texture targets, amounts, a cook-and-freeze checklist and tips. Tap any day to open it.
- **Allergens**: all 15 allergens, when each is planned, and a warning when one hasn't been given for 5 or more days.
- **Foods**: prep notes by stage for 50 foods, with a link to Solid Starts for cutting and serving photos.
- **Log**: everything he's eaten. **GP report** prints a one-page summary of allergens, reactions and foods tried. Export a backup now and then.
- **Safety**: gagging vs choking, choking first aid, reaction signs, when to call 000 or the GP.

## Changing the plan

Open `plan-data.js` on GitHub, click the pencil, edit and commit. Each meal is written as:

```
"What to offer | food ids | allergen ids"
```

Allergen ids end in `:new` for a first try or `:build` for building up. Plain ids mean a keep-up serve. After changing any file, also change `VERSION` in `sw.js` (for example `kavin-solids-v2`) so the phones pick up the update. Close and reopen the app twice to see it.

## Sources

ASCIA Guideline: Infant Feeding for Food Allergy Prevention (January 2026), NHMRC Infant Feeding Guidelines, Pregnancy Birth and Baby (healthdirect), ASCIA peanut introduction guide, RACGP, Nip allergies in the Bub. General guidance only. Check anything specific to Kavin with your GP or child and family health nurse.
