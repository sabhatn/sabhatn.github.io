# Sachin Bhatnagar — personal consulting site

A single, self-contained `index.html` (all CSS and JS inline, no build step, no
frameworks) for **Sachin Bhatnagar — Independent Decision Intelligence Consultant**.

Live URL (once deployed): **https://sabhatn.github.io**

## Files

| File | Purpose |
|------|---------|
| `index.html` | The entire site — HTML, inline CSS, inline JS. |
| `portrait.jpg` | Cropped hero headshot (~57 KB). |
| `glance.jpg` | Optimised one-page "at a glance" overview (~376 KB). |
| `Designer.png` | Source image for `glance.jpg` (kept for reference; not used by the page). |
| `Profile.png` | Earlier source slide (kept for reference; not used by the page). |
| `README.md` | This file. |

> `Sachin_Bhatnagar.docx`, `Designer.png` and `Profile.png` are source/working files —
> they are **not** used by the site and can be deleted or `.gitignore`d before deploy.

## Edit the content

Everything is in **`index.html`**. It's plain HTML, so you can edit any text
directly between the tags. The sections, in order:

1. Hero — name, role, value proposition, focus tags, buttons
2. Outcomes — business results
3. Services — the four service areas
4. Engagements — clearly scoped offerings
5. Why work with me — differentiators
6. Selected work — case-style cards
7. Approach — the five-step method
8. Experience & reach — roles, tools, industries, regions, credentials
9. Book a call — the cal.com embed
10. Footer

### Where the links live (change once, updates everywhere)

Near the **bottom of `index.html`**, inside `<script>`, there's a clearly marked
block:

```js
const CAL_LINK = "https://www.cal.eu/i.sachin.bhatnagar"; // your cal.eu (EU-hosted) scheduling page
const EMAIL    = "i.sachin.bhatnagar@outlook.com";
const LINKEDIN = "https://www.linkedin.com/in/sachinbhatnagarbiwiz/";
```

- **`CAL_LINK`** — your cal.eu scheduling page. It drives the embedded booking
  iframe **and** every "Open booking page" / "Book a call" link. Set it once here.
- **`EMAIL`** — used by the "Email instead" and footer email links (as `mailto:`).
- **`LINKEDIN`** — profile link (also hard-coded in the footer if you change it).

### Swapping the images

- **Hero portrait:** replace `portrait.jpg` (keep the name, or update the `<img src>` in the hero).
- **At-a-glance visual:** replace `profile.jpg`.
- To regenerate the optimised images from a new source PNG, any image editor works;
  aim for < 250 KB and remember to keep the `alt` text accurate.

### Brand / colours

All colours are CSS custom properties at the top of the `<style>` block
(`:root { … }`). The signature accent is `--accent: #e39a2f` (amber); the dark base
is `--ink: #0f1620`. Change them there and the whole site follows.

## Preview locally

From this folder:

```bash
python -m http.server 8000
```

Then open **http://localhost:8000** in your browser. (Any static server works —
e.g. `npx serve` — because there's no build step.)

## Deploy to GitHub Pages (user site)

The site is designed to be published at `https://sabhatn.github.io`:

1. Create a repo named **exactly** `sabhatn.github.io`.
2. Commit and push `index.html`, `portrait.jpg`, `profile.jpg` (and this README)
   to the `main` branch.
3. In the repo: **Settings → Pages → Build and deployment → Deploy from a branch**,
   select **main** / **/ (root)**, Save.
4. Wait a couple of minutes; the site goes live at **https://sabhatn.github.io**.

No Jekyll processing is needed. If you ever add files starting with `_`, add an
empty `.nojekyll` file to the repo root.
