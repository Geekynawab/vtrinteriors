# VTR Projects & Interiors — Website Spec Sheet

**File:** `index.html`
**Hosted:** GitHub Pages — `Geekynawab/vtrinteriors`
**Domain:** `vtrinteriors.com` (GoDaddy DNS — CNAME pending)
**Last updated:** 2026-06-02

---

## Tech Stack

| Item | Detail |
|------|--------|
| Type | Static single-page HTML |
| Hosting | GitHub Pages (free) |
| Fonts | Playfair Display (headings), Inter (body) — Google Fonts |
| Forms | WhatsApp redirect (no backend, no third-party service) |
| Animations | CSS keyframes + vanilla JS |
| Responsive | Yes — breakpoints at 1024px and 640px |

---

## Sections (Top to Bottom)

### 1. Header (Sticky Nav)
- Fixed position, transparent on load, dark on scroll
- Logo: "VTR" (gold, Playfair Display) + "Projects & Interiors" sub-label
- Nav links: About · Services · Process · Partners · Contact · Get a Quote
- "Get a Quote" links to WhatsApp
- **Mobile (≤640px):** Nav hidden, hamburger button shown — opens full-screen drawer with all nav links + WhatsApp CTA

### 2. Hero
- Full-viewport height
- Background: gradient placeholder — **replace with `hero.jpg`** (add file to repo root)
- Visual enhancements: subtle dot grid overlay (CSS), large dim "VTR" watermark behind headline, entrance animations (fadeUp) on all hero elements
- Static headline: **"Visual To Reality"** *(exact client USP — no longer rotating)*
- Italic subheading: **"Crafting spaces"** *(exact client tagline)*
- Gold divider rule (animated on load)
- Description: areas served + project type (from Excel 1.5 and 1.6)
- Stats: **100+** Projects Completed · **2021** Established (from Excel 1.4 and 1.3)
- **Inline contact form** (right column) → WhatsApp on submit
- **Floating WhatsApp icon** (left side, vertical strip) — WhatsApp only for now

### 3. About
- Source: Excel fields 2.1 (bio), 2.2 (philosophy)
- Left: founder photo placeholder — **replace with actual photo when received**
- Right: 3 paragraphs of bio (verbatim from client) + philosophy block (verbatim)
- Philosophy styled as pull-quote with gold left border

### 4. Services Grid
- Source: Excel field 3.1 (exact list) + 3.1 description paragraph
- Layout: 4 columns × 3 rows (12 cards total)
- Each card: SVG icon placeholder + service name + category tag
- **Replace SVG placeholders with actual service photos** — save as `img/service-name.jpg`, add `<img>` tag inside `.svc-img`
- Services (exact from Excel):
  1. Living Room Interiors
  2. Bedroom Interiors (Master/Guest)
  3. Kids Bedroom Interiors
  4. Modular Kitchens
  5. Pooja Room Design
  6. Wardrobe & Storage Solutions
  7. False Ceiling Design
  8. Wallpaper & Wall Treatments
  9. Custom Furniture Design
  10. Office / Commercial Interiors
  11. Turnkey Projects
  12. Renovations & Remodelling

### 5. Process (9 Steps — Alternating Horizontal Timeline)
- Source: Excel field under Section 4 header (exact wording)
- Layout: Sticky horizontal scroll timeline (desktop) / vertical list (mobile ≤768px)
- Alternating: odd steps (1,3,5,7,9) show content **above** the center line; even steps (2,4,6,8) show content **below** the center line — connected by a vertical stem to a dot on the center line
- Behaviour: Section pins to viewport while user scrolls vertically; cards translate horizontally driven by scroll position; each card activates (gold number + full brightness title + glowing dot + gold stem) as it comes into view; gold progress bar + "Step X of 9" counter at bottom
- Steps (verbatim):
  1. Onboarding and consultation
  2. Site measurement and assessment
  3. Design agreement
  4. Concept design & space planning
  5. Client review on layout
  6. Design and development — 2D and 3D
  7. Technical drawings and documents
  8. Contract briefing
  9. Site implementation — bringing life

### 6. Specialties
- Source: Excel field 3.2
- 2 cards (no descriptions — client provided names only):
  - Small Space Maximization
  - Luxury Homes

### 7. Brand Partners (Marquee)
- Source: Excel field 6.2
- Auto-scrolling right-to-left, pauses on hover
- Displayed as **logo placeholder boxes** (branded pill cards with name) — **replace with `<img>` tags once logo files are collected from each brand**
- Add logo files to `logos/` folder, then replace: `<div class="logo-box">BrandName</div>` → `<div class="logo-box"><img src="logos/brandname.png" alt="BrandName"></div>`
- 12 brands (exact from Excel):
  Century · Greenply · Austin · Siam Ply · Gurjan Ply · Hafele · Hettich · Gyproc · Saint Gobain · Ozone · Ebco · Aristo

### 8. Footer
- Source: Excel Section 7
- 3-column layout:
  - Brand name + tagline (from USP) + social icons (WhatsApp, Instagram, Facebook)
  - Contact: email, 2 phone numbers, working hours
  - Areas Served: all 7 localities from Excel 1.5
- Social links: WhatsApp (9849095984), Instagram (Vtr_Interior), Facebook (Vtrprojects)

---

## Forms (Both)

### Inline Hero Form
- Fields: Name, Phone, Area (dropdown), Message
- On submit: opens WhatsApp with pre-filled message to +91 98490 95984
- Message format:
  ```
  Hi Supriyaa, I'm interested in interior design services.
  Name: [name]
  Phone: [phone]
  Area: [area]
  Project: [message]
  ```

### Popup Modal Form
- Same fields and same WhatsApp submission as hero form
- Triggers: when user scrolls past 70% of viewport height (roughly as the hero section ends)
- Frequency: once per browser session (sessionStorage flag)
- Dismiss: click X or click outside modal

---

## Floating Elements

| Element | Position | Behaviour |
|---------|----------|-----------|
| WhatsApp icon (hero) | Left side, vertically centered | Visible only on desktop (hidden ≤1024px) |
| WhatsApp button (global) | Bottom-right, fixed | Always visible, links to WhatsApp |

---

## Pending (Awaiting Client)

| Item | Where to add |
|------|-------------|
| Hero background photo | Save as `hero.jpg` in repo root |
| Founder/team photo | Replace `.about-img-box` placeholder |
| Service photos (12) | Create `img/` folder, save per service, replace `.svc-img` SVGs |
| Instagram, Facebook, YouTube social icons (hero strip) | Add to `.hero-socials` div |
| Awards / certifications | Client said "to be added" — new section when ready |
| Project portfolio photos | New section — add when photos received |
| Client testimonials | New section — add when provided |

---

## DNS / Deployment Status

| Step | Status |
|------|--------|
| GitHub Pages enabled | Done |
| CNAME file in repo | Done (`vtrinteriors.com`) |
| GoDaddy CNAME record | Pending — needs OTP from Supriyaa |
| HTTPS enforcement | Pending — enable after DNS propagates |

**GoDaddy CNAME to add:**
- Type: `CNAME`
- Name: `www`
- Value: `geekynawab.github.io`
- TTL: 1 Hour

---

## Design Reference

| Site | Elements borrowed |
|------|------------------|
| chattelsdesign.com | Overall structure, hero + inline form, brand marquee, about layout |
| arkarchitects.co.in | Service cards grid, process section numbered layout |

---

## Color Palette

| Name | Hex |
|------|-----|
| Gold | `#d4a843` |
| Gold (dim) | `#a08860` |
| Cream | `#f5e8c8` |
| Background (main) | `#0f0b06` |
| Background (alt sections) | `#120d05` |
| Muted text | `#8a7050` |
| WhatsApp green | `#25D366` |
