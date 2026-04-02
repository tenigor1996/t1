# Digital Signage Dashboard

A full-screen browser-based digital signage dashboard built with vanilla HTML/CSS/JS, deployed on Vercel.

**Live:** https://t1-gray-xi.vercel.app

---

## Features

### Widgets
- **Upcoming Events** (top-right) — compact badge by default, click to expand full event list
- **Time & Weather** (bottom-right) — compact single card by default, click to expand with Wind / Humidity / Feels Like / UV Index
- Both widgets are **draggable** (hover to reveal handle), **removable** (✕ button), and **restorable** (banner at top)
- Positions and states persist via `localStorage`

### Calendar
- Current week view, centered on screen
- **← → arrows** and **mouse wheel** to navigate between weeks
- **Today** button snaps back to current week
- Click any day to **add or remove events** via modal
- Color-coded event pills: white = public holidays, blue = custom user events

### Commercial Strip
- Dark scrolling ticker at the bottom with emoji + text + tag sections
- **✎ button** opens editor to add or remove sections
- Content persists via `localStorage`

### Background
- Full-screen image carousel (Unsplash), crossfades every 8 seconds
- Vignette overlay for readability

---

## Project Structure

```
t1/
├── index.html        # Main dashboard (single-file app)
├── landing.html      # Info/landing page
├── assets/
│   └── logos/        # SVG brand logos for commercial strip
├── vercel.json       # Vercel config
└── README.md
```

---

## Deployment

Deployed automatically via Vercel on every push to `main`.

To run locally:
```bash
# Just open index.html in a browser, or use any static server:
npx serve .
```

---

## Data Sources

| Data | Source |
|------|--------|
| Weather | [Open-Meteo API](https://open-meteo.com) (NYC, no key required) |
| Public Holidays | [date.nager.at](https://date.nager.at) (US holidays, no key required) |
| Background images | [Unsplash](https://unsplash.com) |

---

## localStorage Keys

| Key | Contents |
|-----|----------|
| `events` | User-added calendar events |
| `commercial_sections` | Commercial strip sections |
| `pos_widget-events` | Events widget position |
| `pos_widget-clock` | Clock widget position |
| `size_events` | Events widget size (compact/expanded) |
| `size_clock` | Clock widget size |
| `hidden_widgets` | Which widgets are hidden |
