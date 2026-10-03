# Hendy & Fitri — Wedding Invitation

## 1. Google Sheet + Apps Script
1. Create a Google Sheet "Wedding RSVP". Extensions > Apps Script, paste `Code.gs`.
2. Run `setup` once (approve permissions). It creates tabs **RSVP** (Timestamp, Name, Attending, Guests) and **Wishes** (Timestamp, Name, Wish).
3. Deploy > New deployment > Web app. Execute as: **Me**. Access: **Anyone**. Copy the Web App URL.
4. Paste it into `CONFIG.SCRIPT_URL` in `index.html`.
After editing Code.gs, use Deploy > Manage deployments > Edit > New version (URL stays the same).

## 2. GitHub Pages
Create a repo, upload all files (keep `images/` and `assets/`), then Settings > Pages > Deploy from branch `main` / root.
Site: `https://<username>.github.io/<repo>/`

## 3. Maintenance
- Everything editable is in the `CONFIG` block at the top of `index.html` (events, maps, bank, address, music, photos).
- Photos: replace `images/hero.jpg` and `images/1.jpg`–`10.jpg` (keep names), or add paths to `GALLERY`. Compress to ≤300 KB each.
- Backgrounds: `images/cover.jpg` (cover page) and `images/bg.jpg` (rest of the page, parallax). The cover falls back to `bg.jpg` if `cover.jpg` is missing.
- Music: put an MP3 at `assets/music.mp3` (browsers only autoplay after the guest taps "Open Invitation").
- Guest links: `https://<site>/?to=Mr.%20Budi%20%26%20Family` (space = `%20`, & = `%26`). In a Sheet with names in A2: `="https://<site>/?to="&ENCODEURL(A2)`.
- Fill bank/address by replacing `XXX` in CONFIG.
