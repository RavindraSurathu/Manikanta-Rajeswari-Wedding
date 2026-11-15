# 🪔 Manikanta ♡ Rajeswari — Wedding Invitation

A temple-themed animated wedding invitation for
**Chi. Naga Sai Manikanta Teja** with **Chi. La. Sow. Rajeswari**.

**Sumuhurtham:** Saturday, 21 November 2026, 8:52 PM · Sri Balaji Convention, Penugonda
**Reception & Dinner:** Sunday, 22 November 2026, 7:00 PM · Sangepu Kalyanamandapam, Gosala

**Live link:** https://ravindrasurathu.github.io/Manikanta-Rajeswari-Wedding/

---

## 📸 Photo guide

All photos live in the `images/` folder. The page looks for these exact file names:

| File | Where it appears | Best shape |
|------|------------------|-----------|
| `couple.jpg` | **The Bride & Groom**: large temple-arch portrait | Portrait (4:5 or 3:4) |
| `band.jpg` | Full-screen photo behind *"Two hearts, one promise"* | Portrait or square, subject in centre |
| `j1.jpg` – `j4.jpg` | **Our Journey**: one photo per step | Any; the top part of the photo is shown |
| `1.jpg` – `6.jpg` | **Moments We Cherish** gallery | Portrait (4:5 or 3:4) |
| `music.mp3` *(optional, put it next to `index.html`)* | Background song | Under 5 MB |

### Replace a photo
1. Rename your new photo to the same name as the one you're replacing (for example `couple.jpg`).
2. Open the `images` folder on GitHub → **Add file → Upload files** → drop it in → **Commit changes**.
3. Wait 1–2 minutes and refresh the live link.

### Add more photos to "Moments We Cherish"
1. Upload them as `7.jpg`, `8.jpg`, … in the `images` folder.
2. In `index.html`, find this line and change `6` to the new total:
   ```js
   gallery: Array.from({length: 6}, (_, i) => ({ src: `images/${i + 1}.jpg` })),
   ```
   Tip: keep it at 6, 9 or 12 so the grid stays even on both phones and laptops.

### Remove photos from the gallery
Lower the number in the same line (for example `length: 3` shows only `1.jpg` to `3.jpg`).

### Add a video to the gallery
Upload `images/video.mp4` (under ~20 MB) and change the gallery line to:
```js
gallery: [...Array.from({length: 6}, (_, i) => ({ src: `images/${i + 1}.jpg` })), { src: "images/video.mp4", type: "video" }],
```

### Keep the page fast
Phone photos are often 5–10 MB. Resize them to about **1080 px wide** and **under 400 KB** before uploading
(https://squoosh.app works well), otherwise guests on mobile data will wait for them to load.
If a photo is missing, the page shows a gold placeholder with the expected file name instead of breaking.

---

## ✏️ Changing text, dates or venues

Everything is in the `CONFIG` block at the top of `index.html`: names, parents, muhurtham time (drives the countdown),
events, venues and Google Maps links, invited-by and contacts. Edit it on GitHub with the ✏️ pencil icon → **Commit changes**.

To show phone numbers, fill in `contacts`, e.g.
```js
contacts: [ { name: "Srihari", phone: "+91 90000 00000" } ],
```

## 🌐 Turning on GitHub Pages (one time)
Repo **Settings → Pages → Source: Deploy from a branch → Branch: `main` / `(root)` → Save**.
The link above goes live within a couple of minutes.
