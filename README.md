# 🪔 Manikanta ♡ Rajeswari — Wedding Invitation

A temple-themed animated wedding invitation for
**Chi. Naga Sai Manikanta Teja** with **Chi. La. Sow. Rajeswari**.

**Sumuhurtham:** Saturday, 21 November 2026, 8:52 PM · Sri Balaji Convention, Penugonda
**Reception & Dinner:** Sunday, 22 November 2026, 7:00 PM · Sangepu Kalyanamandapam, Gosala

**Live link:** https://vivaahcreations.com/Manikanta-Rajeswari-Wedding/

---

## 📸 Photo guide

All photos live in the `Manikanta-Rajeswari-Wedding/images/` folder. The page looks for these exact file names:

| File | Where it appears | Best shape |
|------|------------------|-----------|
| `couple.jpg` | **The Bride & Groom**: large temple-arch portrait | Portrait (4:5 or 3:4) |
| `band.jpg` | Full-screen photo behind *"Two hearts, one promise"* | Portrait or square, subject in centre |
| `j1.jpg` – `j4.jpg` | **Our Journey**: one photo per step | Any; the top part of the photo is shown |
| `1.jpg` – `6.jpg` | **Moments We Cherish** gallery | Portrait (4:5 or 3:4) |
| `music.mp3` *(optional, in `Manikanta-Rajeswari-Wedding/`)* | Background song | Under 5 MB |

### Replace a photo
1. Rename your new photo to the same name as the one you're replacing (for example `couple.jpg`).
2. Open `Manikanta-Rajeswari-Wedding/images` on GitHub → **Add file → Upload files** → drop it in → **Commit changes**.
3. Wait 1–2 minutes and refresh the live link.

### Add more photos to "Moments We Cherish"
1. Upload them as `7.jpg`, `8.jpg`, … in `Manikanta-Rajeswari-Wedding/images`.
2. In `Manikanta-Rajeswari-Wedding/index.html`, find this line and change `6` to the new total:
   ```js
   gallery: Array.from({length: 6}, (_, i) => ({ src: `images/${i + 1}.jpg` })),
   ```
   Tip: keep it at 6, 9 or 12 so the grid stays even on both phones and laptops.

### Remove photos from the gallery
Lower the number in the same line (for example `length: 3` shows only `1.jpg` to `3.jpg`).

### Add a video to the gallery
Upload `Manikanta-Rajeswari-Wedding/images/video.mp4` (under ~20 MB) and change the gallery line to:
```js
gallery: [...Array.from({length: 6}, (_, i) => ({ src: `images/${i + 1}.jpg` })), { src: "images/video.mp4", type: "video" }],
```

### Keep the page fast
Phone photos are often 5–10 MB. Resize them to about **1080 px wide** and **under 400 KB** before uploading
(https://squoosh.app works well), otherwise guests on mobile data will wait for them to load.
If a photo is missing, the page shows a gold placeholder with the expected file name instead of breaking.

---

## ✏️ Changing text, dates or venues

Everything is in the `CONFIG` block at the top of `Manikanta-Rajeswari-Wedding/index.html`: names, parents, muhurtham time (drives the countdown),
events, venues and Google Maps links, invited-by and contacts. Edit it on GitHub with the ✏️ pencil icon → **Commit changes**.

### 🇮🇳 Telugu / English switch
The gold **EN | తెలుగు** switch (bottom-left, also on the opening screen) flips the whole page between English and Telugu.
Each guest's choice is remembered on their phone. To share a link that opens straight in Telugu, add `#te` to the end:
`https://vivaahcreations.com/Manikanta-Rajeswari-Wedding/#te`. The WhatsApp button does this automatically when Telugu is on,
and sends the Telugu message.

Where to edit the text:
- `CONFIG` holds the English details, and `TELUGU` (just below it) the Telugu versions of the same details. Anything missing from `TELUGU` falls back to English.
- `TEXT.en` / `TEXT.te` hold the headings, buttons and labels. Setting an entry to `""` hides it in that language.
- `whatsapp` inside `CONFIG` and `TELUGU` is the share message for each language.

To show phone numbers, fill in `contacts`, e.g.
```js
contacts: [ { name: "Srihari", phone: "+91 90000 00000" } ],
```

## 🌐 Hosting & custom domain
Served by GitHub Pages from the `main` branch (root):

| Address | File |
|---|---|
| https://vivaahcreations.com/ | `index.html` — Vivaah Creations landing page |
| https://vivaahcreations.com/Manikanta-Rajeswari-Wedding/ | `Manikanta-Rajeswari-Wedding/index.html` — this invitation |

Paths are case-sensitive: keep the folder name exactly `Manikanta-Rajeswari-Wedding`.
To add another couple's invitation, copy the `Manikanta-Rajeswari-Wedding` folder, rename it (e.g. `Ravi-Priya-Wedding`), edit its CONFIG and photos,
and add a card for it on the landing page.

- The `CNAME` file in this repo tells GitHub Pages to use `vivaahcreations.com`. Don't delete it.
- DNS for `vivaahcreations.com` (Namecheap domain, Custom DNS → AWS Route 53, or Namecheap BasicDNS):

| Name | Type | Value |
|------|------|-------|
| `@` (apex) | A | `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153` |
| `www` | CNAME | `ravindrasurathu.github.io` |

- The old link `https://ravindrasurathu.github.io/Manikanta-Rajeswari-Wedding/` redirects to https://vivaahcreations.com/ (the landing page), which links to the invitation.
- Repo **Settings → Pages**: custom domain `vivaahcreations.com`, **Enforce HTTPS** ticked.
