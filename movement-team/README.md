# Movement Team Physiotherapy & Rehabilitation — Website

Single-file 3D website for Movement Team Physiotherapy & Rehabilitation, Ahmedabad.

**Live site:** _(add your GitHub Pages URL here after deploying)_

---

## What's in this repo

| File | Purpose |
|------|---------|
| `index.html` | The entire website — HTML, CSS, JavaScript, WebGL shaders and the team photo are all inside this one file |
| `README.md` | This file |
| `.gitignore` | Keeps OS junk files out of the repo |

There is no build step, no `npm install`, no dependencies to install. Open `index.html` in any browser and it runs.

---

## Deploying to GitHub Pages (free hosting)

1. Push this folder to a GitHub repository.
2. In the repo, go to **Settings → Pages**.
3. Under **Source**, choose **Deploy from a branch**.
4. Set branch to `main` and folder to `/ (root)`. Click **Save**.
5. Wait 1–2 minutes. Your site appears at `https://<your-username>.github.io/<repo-name>/`.

### Using a custom domain (e.g. movementteamphysio.com)

1. Buy the domain from any registrar.
2. In **Settings → Pages → Custom domain**, enter the domain and save.
3. At your registrar, add these DNS records:

   | Type | Name | Value |
   |------|------|-------|
   | A | @ | 185.199.108.153 |
   | A | @ | 185.199.109.153 |
   | A | @ | 185.199.110.153 |
   | A | @ | 185.199.111.153 |
   | CNAME | www | `<your-username>.github.io` |

4. Tick **Enforce HTTPS** once the certificate is issued.

---

## Editing the site

### Phone number

All call, WhatsApp and header links read from one place. Search `index.html` for `CONFIG` (near the bottom, inside the `<script>` tag):

```js
const CONFIG = {
  PHONE_TEL  : '+917096633936',
  PHONE_SHOW : '+91 70966 33936',
  WA_MESSAGE : 'Hello Movement Team Physiotherapy, I would like to book a physiotherapy appointment.'
};
```

Change those values and every one of the 18 contact points on the page updates.

### Team photos

Dr. Parth K Makwana's photo is embedded directly in the file as base64.

Dr. Khushboo Gohel and Dr. Pravin Timbal still show placeholder cards. To add their photos:

1. Create an `images/` folder in this repo and add the files.
2. In `index.html`, find the placeholder block for that doctor:

```html
<div class="ph-holder">
  <svg ...></svg>
  <span>Add photo:<br>images/dr-khushboo-gohel.jpg</span>
</div>
```

3. Replace the whole `<div class="ph-holder">…</div>` with:

```html
<img src="images/dr-khushboo-gohel.jpg" alt="Dr. Khushboo Gohel, Consultant Physiotherapist" width="700" height="875" loading="lazy" decoding="async">
```

Portrait images at roughly 4:5 ratio (e.g. 700×875) work best.

### Testimonials

**These are placeholders and must be replaced before the site goes public.**

Search for `Replace with a real Google review`. There are four cards. Paste in genuine reviews from your Google Business profile, and update the patient name and branch under each one.

Fabricated testimonials for a medical practice breach ASCI advertising guidelines and consumer protection rules in India. Use real reviews only.

---

## Technical notes

- **3D:** Three.js r128 particle system that morphs between a vertebral column, a DNA double helix and an orb, scrubbed to scroll position. One WebGL context for the whole page.
- **Performance:** device-tiered particle counts (5,200 desktop / 3,000 low-power / 1,800 mobile), pixel ratio capped, plus a runtime FPS guard that halves the workload automatically if the first three seconds average under 45fps.
- **Maps:** both Google Maps embeds load only when tapped, so there are zero third-party iframes on first paint.
- **Accessibility:** WCAG 2.1 AA contrast verified on all text/surface pairs, 48px minimum tap targets, visible focus states, and `prefers-reduced-motion` honoured.
- **SEO:** `MedicalClinic` structured data (schema.org) covering both branch addresses, opening hours, aggregate rating and all three clinicians.

Libraries load from CDN (Three.js, GSAP, Google Fonts), so the site needs an internet connection to display the 3D and the custom typeface.

---

## Clinic details encoded in this site

**Naranpura branch**
A/4, Second Floor, Ankur Road, near Kalupur Bank, Prahalad Society, Rang Jyot Society, Naranpura, Ahmedabad, Gujarat 380013

**Maninagar branch**
2nd Floor, Block-A, No. 7/B, Rajratna Arcade, opp. Satyam Tower, nr. Maninagar Railway Station Road, Maninagar, Ahmedabad, Gujarat 380008

**Hours:** Monday–Saturday, 9:00 AM – 10:00 PM · Sunday closed
**Phone:** +91 70966 33936
**Instagram:** [@movement.team.physio.fitness](https://www.instagram.com/movement.team.physio.fitness/)
