# 🌍 Time Zone Converter

A lightweight, single-file web application for viewing live clocks across multiple time zones and converting specific times between them — no frameworks, no dependencies, no build step required.

---

## Features

- **Live clocks** — all added time zones update every second in real time
- **12h / 24h toggle** — switch time formats across all clocks instantly
- **Abbreviation search** — find zones by short code (`CST`, `IST`, `PST`, `JST`, `CET`, etc.), city name, or full zone name
- **Difference indicator** — each zone shows how far ahead or behind it is relative to your reference zone (green = ahead, orange = behind)
- **Time converter** — pick any time and source zone, instantly see the equivalent time in all other added zones
- **Quick-add chips** — one-click buttons for popular zones (Mumbai/Delhi, New York, London, Tokyo, UTC)
- **44 pre-loaded zones** — covers all major cities and regions worldwide
- **Zero dependencies** — pure HTML, CSS, and JavaScript; works offline after first load (fonts require internet)

---

## Getting Started

No installation needed. Just open the file in any modern browser.

```bash
# Clone or download the file, then open it
open index.html
```

Or simply double-click `index.html` in your file explorer.

---

## Usage

### Adding Time Zones

- Type a **city name** (e.g. `Tokyo`, `Paris`, `Dubai`) in the search box
- Type a **time zone abbreviation** (e.g. `CST`, `IST`, `PST`, `AEST`, `GMT`) to find matching zones
- Type a **region or full name** (e.g. `Eastern Time`, `India Standard Time`)
- Click any result in the dropdown to add it
- Use the **quick-add chips** below the search bar for one-click access to popular zones

### Reading the Clocks

Each zone card shows:
- **Country code badge** — colour-coded by country/region
- **City name and time zone label**
- **UTC offset** (e.g. `UTC+5:30`)
- **Live time** — updates every second
- **Date** — shown in `Day, Mon DD` format
- **Difference** from your reference zone — the first zone added is always the reference (highlighted with a blue border)

### Converting a Specific Time

1. Scroll to the **Convert a specific time** section at the bottom
2. Enter your desired time using the time picker
3. Select the **source time zone** from the dropdown
4. All other added zones immediately show the equivalent converted time

### Removing a Zone

Click the **×** button on the right side of any zone card to remove it.

---

## Supported Search Terms

| Input | Matches |
|-------|---------|
| `CST` | Chicago (US), Mexico City, Shanghai |
| `IST` | Mumbai / Delhi |
| `PST` / `PDT` | Los Angeles, Vancouver |
| `EST` / `EDT` | New York, Toronto |
| `GMT` / `BST` | London |
| `CET` / `CEST` | Paris, Berlin, Rome, Amsterdam, Madrid, Stockholm |
| `JST` | Tokyo |
| `KST` | Seoul |
| `AEST` / `AEDT` | Sydney, Melbourne |
| `MSK` | Moscow |
| `GST` | Dubai |
| `PKT` | Karachi |
| `NPT` | Kathmandu |
| `IST` | Mumbai / Delhi |
| `UTC` / `GMT` | UTC |

---

## Included Time Zones

| Region | Cities |
|--------|--------|
| **North America** | New York, Los Angeles, Chicago, Denver, Toronto, Vancouver, Mexico City, Honolulu |
| **South America** | São Paulo |
| **Europe** | London, Paris, Berlin, Moscow, Istanbul, Amsterdam, Madrid, Rome, Stockholm |
| **Africa** | Cairo, Johannesburg, Lagos, Nairobi |
| **Middle East** | Dubai, Riyadh, Tehran |
| **South Asia** | Mumbai/Delhi, Karachi, Dhaka, Kathmandu, Colombo, Yangon |
| **Southeast Asia** | Bangkok, Singapore, Jakarta, Hong Kong, Taipei |
| **East Asia** | Shanghai, Seoul, Tokyo |
| **Oceania** | Sydney, Melbourne, Perth, Auckland |
| **Universal** | UTC |

---

## Browser Support

Works in all modern browsers that support the `Intl.DateTimeFormat` API:

| Browser | Minimum Version |
|---------|----------------|
| Chrome | 24+ |
| Firefox | 29+ |
| Safari | 10+ |
| Edge | 12+ |

> **Note:** Google Fonts (Sora, DM Mono) require an internet connection to load. The app functions fully without them, falling back to system sans-serif fonts.

---

## Customisation

All configuration lives inside `index.html` in the `<script>` block.

**Add a new time zone** — append an entry to the `ZONES` array:

```js
{
  id:    'America/Phoenix',       // IANA timezone ID
  name:  'Phoenix',               // Display name
  sub:   'Mountain Standard Time',// Subtitle / full name
  code:  'US',                    // Country code (shown as badge)
  color: '#DBEAFE',               // Badge background colour
  tc:    '#1E40AF',               // Badge text colour
  abbr:  ['mst', 'arizona']       // Search abbreviations (lowercase)
}
```

**Change the default zone** — update the `active` array and `refZone`:

```js
let active  = ['America/New_York'];
let refZone = 'America/New_York';
```

**Change quick-add chips** — edit the `QUICK` array:

```js
const QUICK = ['America/New_York', 'Europe/London', 'Asia/Tokyo', 'UTC'];
```


