# WEDEPART2
# st10506739WEDEPART2
# HER Foundation Website

A responsive, multi-page website for **H.E.R Foundation** — a non-profit supporting and empowering women, children, and families in need across South Africa. *Honoured · Empowered · Rooted.*

## About

HER FOUNDATION is a lifestyle and sisterhood initiative for young women within St John's Apostolic Faith Mission Church & beyond. It was birthed out of growing need to intentionally support young women beyond spiritual gatherings alone- by encouraging holistic growth in faith, lifestyle, education, career, health and personal development.HER. FOUNDATION addresses everyday gaps in basic needs through food parcels, clothing drives, sanitary product distribution, and church community outreach programmes. This site shares the organisation's story, outlines its programmes, and gives visitors a way to donate, volunteer, or partner.

## Pages

| Page | File | Purpose |
|---|---|---|
| Home | `index.html` | Introduction, mission statement, impact overview |
| About | `about.html` | Our story, mission & vision, who we serve |
| Services | `services.html` | Breakdown of the three core programmes |
| Get Involved | `enquiry.html` | Donate / volunteer / partner enquiry form |
| Contact | `contact.html` | Contact details, map placeholder, social links |

## Built With

- **HTML5** — semantic page structure
- **CSS3** — custom design system (CSS variables, responsive grid/flexbox, no framework)
- **Vanilla JavaScript** — mobile navigation toggle, form validation, dynamic footer year
- **Google Fonts** — [Fraunces](https://fonts.google.com/specimen/Fraunces) (display) & [Inter](https://fonts.google.com/specimen/Inter) (body)

## Project Structure

```
her-foundation/
├── index.html
├── about.html
├── services.html
├── enquiry.html
├── contact.html
├── css/
│   └── style.css
├── js/
│   └── script.js
└── images/
    └── logo.jpg
```

## Responsive Design

The layout uses a mobile-first set of breakpoints, defined with `em`/`rem` and `%`-based sizing rather than fixed pixels wherever possible:

| Breakpoint | Range | Layout |
|---|---|---|
| Desktop | 1025px and up | Multi-column grids (impact cards, contact cards), full horizontal nav |
| Tablet | 721px – 1024px | 2-column grids, wider touch targets |
| Mobile | 720px and below | Single-column layout, collapsible hamburger nav, stacked buttons |
| Small mobile | 400px and below | Reduced heading scale for narrow phones |

Images use explicit `width`/`height` attributes (to prevent layout shift) and `loading="lazy"`.

### Screenshot evidence

Add screenshots of the site at each breakpoint here before submission, e.g.:

```
screenshots/
├── home-desktop.png
├── home-tablet.png
├── home-mobile.png
├── enquiry-desktop.png
├── enquiry-tablet.png
└── enquiry-mobile.png
```

Capture these using your browser's device toolbar (desktop ≈1440px, tablet ≈820px, mobile ≈390px) and reference them here, e.g.:

`![Home page – desktop](screenshots/home-desktop.png)`

## Getting Started

No build tools or dependencies required — this is a static site.

1. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/<your-repo>.git
   ```
2. Open `index.html` in your browser, or serve it locally:
   ```bash
   npx serve .
   ```

## Features

- Fully responsive layout with a mobile hamburger menu
- Accessible markup (skip link, focus states, semantic landmarks, alt text)
- Client-side validation on the Get Involved form (name & email)
- Consistent, reusable design tokens defined in `css/style.css`

## Roadmap

- [ ] Connect the enquiry form to a backend or form service (e.g. Formspree, Netlify Forms)
- [ ] Embed a live Google Map on the Contact page
- [ ] Add real photography to replace placeholder content
- [ ] Link up live social media accounts

## Contact

**Email:** info@herfoundation.github.io
**Phone:** +27 79 745 1840

## Adding your own photos

The Home hero, Home impact cards, About "Our Story" section, and each Services programme card now have a labelled placeholder image in `images/` so the layout is finished ahead of real content. To swap one in:

1. Add your photo to `images/` (e.g. `images/hero-photo.jpg`). Keep it under ~300KB — compress with [Squoosh](https://squoosh.app) or similar, and prefer `.webp`/`.jpg`.
2. In the relevant HTML file, change the placeholder `src` (e.g. `images/placeholder-hero.svg`) to your file's path, and update the `alt` text to describe the real photo.
3. No CSS changes are needed — every photo slot (`.hero-media img`, `.impact-photo`, `.story-media img`, `.programme-photo`) is already sized and made responsive with `object-fit: cover`.

Placeholder → intended replacement:

| Placeholder | Used on | Replace with |
|---|---|---|
| `placeholder-hero.svg` | Home hero | `hero-photo.jpg` — portrait community/women photo |
| `placeholder-story.svg` | About "Our Story" | `story-photo.jpg` — landscape sisterhood/founder photo |
| `placeholder-programme-01.svg` / `02` / `03` | Home impact cards & Services programmes | `programme-0N.jpg` — square-ish photo per programme |
| `placeholder-programme-04.svg` | Home "Outreach" impact card | `programme-04.jpg` |

### Embedding video

To add a video (e.g. a YouTube clip on the About or Get Involved page), wrap the embed so it stays responsive:

```html
<div class="video-wrap">
    <iframe src="https://www.youtube.com/embed/VIDEO_ID" title="HER Foundation" allowfullscreen loading="lazy"></iframe>
</div>
```

```css
.video-wrap { position: relative; aspect-ratio: 16 / 9; }
.video-wrap iframe { position: absolute; inset: 0; width: 100%; height: 100%; border: 0; border-radius: var(--radius); }
```

Ask if you'd like this added to a specific page once you have the video link.

## Changelog

All notable changes to this project are documented below, newest first.

### Part 2 — Photo layout

- **Added:** Responsive photo slots across the site — a split hero (text + image) on Home, a thumbnail on every impact card, a photo beside "Our Story" on About, and a photo on every programme card on Services.
- **Added:** On-brand labelled placeholder graphics (`images/placeholder-*.svg`) for each slot so the site is visually complete before real photography is available; see "Adding your own photos" above for how to swap them in.
- **Added:** CSS for `.hero-inner`, `.hero-media`, `.impact-photo`, `.story-media`, and `.programme-photo`, all responsive — the hero image moves above the text on tablet/mobile, and programme photos reflow below the title on mobile using `grid-template-areas`.
- **Documented:** A responsive video-embed pattern for future YouTube/Vimeo content.

### Part 2 — Designing the Visuals (CSS Styling & Responsive Design)

- **Fixed:** Organised project files into the documented folder structure — moved `style.css` into `css/`, `script.js` into `js/`, and the logo into `images/logo.jpg`, and updated every page's `<link>`, `<script>`, and `<img>` references to match.
- **Fixed:** Corrected a typo in the homepage hero eyebrow text ("Hohoured" → "Honoured").
- **Fixed:** Repaired malformed markup on `contact.html` — an unclosed `<div class="contact-card">` was breaking the layout of the Follow Us card.
- **Added:** A "Visit Us" contact card with a map placeholder on `contact.html`, matching what the README described but was missing from the page.
- **Added:** A tablet breakpoint (`max-width: 1024px`) so the impact grid and contact grid step down to two columns before collapsing to one on mobile, instead of jumping straight from desktop to mobile styling.
- **Improved:** Mobile styles for the hero section (fluid heading size with `clamp()`, full-width stacked call-to-action buttons) and for form buttons on the Get Involved page.
- **Added:** A small-mobile breakpoint (`max-width: 400px`) for narrower phone screens.
- **Added:** `width`, `height`, and `loading="lazy"` attributes on the logo image across all pages to reduce layout shift and improve load performance — first step toward the responsive-image guidance in the brief.
- **Fixed:** Added the missing "Partner with us" option to the enquiry type dropdown on `enquiry.html`, matching the donate/volunteer/partner options described in the project proposal.
- **Fixed:** Corrected the contact phone number in the README to match the number used on `contact.html` (+27 79 745 1840).

### Part 1 — Structure & Content (feedback corrections)

- Implemented corrections based on Part 1 marker feedback (see submission notes for the specific items addressed).
- Confirmed semantic HTML structure, skip link, and alt text across all five pages.

## References

- Afrihost. 2026. *Web Hosting Solutions*. Available at: https://www.afrihost.com (Accessed: 21 August 2026).
- GitHub. 2026. *GitHub Documentation*. Available at: https://docs.github.com (Accessed: 21 August 2026).
- MDN Web Docs. 2026. *HTML: HyperText Markup Language*. Available at: https://developer.mozilla.org/en-US/docs/Web/HTML (Accessed: 21 August 2026).
- MDN Web Docs. 2026. *CSS: Cascading Style Sheets*. Available at: https://developer.mozilla.org/en-US/docs/Web/CSS (Accessed: 21 August 2026).
- MDN Web Docs. 2026. *JavaScript Guide*. Available at: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide (Accessed: 21 August 2026).
- MDN Web Docs. 2026. *Using media queries*. Available at: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_media_queries/Using_media_queries (Accessed: 23 September 2026).
- Nielsen Norman Group. 2026. *User Experience Basics*. Available at: https://www.nngroup.com/articles/definition-user-experience (Accessed: 21 August 2026).
- Visual Studio Code. 2026. *Visual Studio Code Documentation*. Available at: https://code.visualstudio.com/docs (Accessed: 21 August 2026).
- W3Schools. 2026. *HTML Tutorial*. Available at: https://www.w3schools.com/html (Accessed: 21 August 2026).
- W3Schools. 2026. *CSS Tutorial*. Available at: https://www.w3schools.com/css (Accessed: 21 August 2026).
- W3Schools. 2026. *CSS Responsive Web Design*. Available at: https://www.w3schools.com/css/css_rwd_intro.asp (Accessed: 23 September 2026).
- W3Schools. 2026. *JavaScript Tutorial*. Available at: https://www.w3schools.com/js (Accessed: 21 August 2026).
- Xneelo. 2026. *Website Hosting Services*. Available at: https://xneelo.co.za (Accessed: 21 August 2026).

## License

This project is provided for HER. Foundation's use. Add a license of your choice here (e.g. MIT) if you'd like to open it up for reuse.
