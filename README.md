# Rahul Weds Aishwarya — Wedding Website

A single-page, fast, and mobile-friendly wedding website built with React 18 (UMD) and Tailwind CSS (CDN)—no build step needed. Just open `index.html` and you’re live.

## 🌐 URL

- <https://rahulwedsaishwarya.in/>

## ✨ Features

- Zero-build setup: React + Tailwind via CDN, JSX compiled in-browser with Babel.
- Hero countdown to the big day.
- Events grouped by date with image cards.
- Venue section with “Open in Maps”.
- Travel & Stay info cards with quick links.
- FAQ accordion.
- RSVP form embedded via Tally.
- Dark mode toggle (remembers your choice in `localStorage`).
- Polished UI with soft borders, shadows, and responsive layout.
- Section icons on both sides of titles (e.g., 📍 Venue shows icons left & right).

## 🗂️ Project Structure

```
wedding-site/
├─ index.html        # All React components + content live here
├─ images/
│  ├─ hero-photo.png
│  ├─ google_maps.svg
│  ├─ event-placeholder.jpg
│  └─ events/
│     ├─ mehendi.jpg
│     ├─ haldi.jpeg
│     ├─ ring.jpeg
│     ├─ marriage.jpeg
│     └─ reception.jpeg
└─ (optional) README.md
```

## 🚀 Getting Started

### Option 1: Just open the file

Double-click `index.html`. This works for most setups.

### Option 2: Serve locally (recommended)

Avoids any browser security quirks with local files.

**Python 3**

```bash
# from the project folder
python3 -m http.server 8080
# open http://localhost:8080
```

**Node (http-server)**

```bash
npx http-server -p 8080
```

## 🧩 Tech Stack

- React 18 UMD (`react` / `react-dom` via unpkg)
- Tailwind CSS (CDN)
- Babel Standalone (compiles JSX in the browser)
- Vanilla JS for small utilities (theme, countdown)
- Tally for RSVP embed

## 🔧 How to Customize

Open `index.html` and edit the `content` object inside the `<script type="text/babel">` block:

- Couple bios: `content.couple`
- Date/City/Venue: `content.wedding`
- Story text: `content.story`
- Events (name, dateLabel, time, venue, map URL, image): `content.events`
- Venue details + map: `content.venue`
- Travel cards: `content.travel.viaTrain` & `content.travel.viaFlight`
- FAQ: `content.faq`
- RSVP link: `content.rsvp.link`

### Images

Place new images in `images/` (or `images/events/`) and update the paths in the `content` object.

### Section Icons (left & right)

Each section uses:

```jsx
<Section id="rsvp" title="RSVP" icon="✉️">
```

If the `icon` prop is provided, the icon appears on **both the left and right sides** of the title automatically.

## Theme (Light/Dark)

- Default is light unless `localStorage["wedding.theme"] === "dark"`.
- Toggle using the header button. Preference is saved between visits.

## 📨 RSVP (Tally) Notes

- The Tally embed initializes on mount. If you modify the form link, update:

```html
<iframe data-tally-src="https://tally.so/embed/XXXXXX?..."></iframe>
```

- The script loader is included at the top and re-initialized inside React to handle SPA behavior.

## 🌐 Deploy (GitHub Pages)

1. Push the project to GitHub in a public repo.
2. In **Settings → Pages**, set:
   - **Source:** `main` (or your default branch)
   - **Folder:** `/` (root)
3. Wait for the green check → your site URL is live.

**Tip:** Since it’s a pure static site, Netlify or Vercel works great too.

## 🛠️ Development Tips

- Keep the `images/google_maps.svg` file path correct (used in buttons).
- If the Tally form doesn’t load:
  - Ensure the embed script is reachable (`https://tally.so/widgets/embed.js`).
  - Check browser extensions that might block iframes.
- For best performance, optimize images (e.g., 1600px wide, JPEG/WebP).

## ✅ Accessibility & SEO

- Descriptive alt text for images.
- Meaningful section titles and headings.
- Basic metadata:
  - `<title>` and `<meta name="description">` are set in the `<head>`.
- Smooth scrolling for anchor links.

## 📄 License

Personal use. If you fork, feel free to adapt for your own wedding!
