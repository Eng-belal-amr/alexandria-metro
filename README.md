# 🚇 Alexandria Metro — Official Information Portal
### مترو الإسكندرية — البوابة الرسمية للمعلومات

> A full-featured, bilingual (Arabic/English) web portal for the Alexandria Metro Line 1 project.  
> Built as a single-file static website — no frameworks, no build tools, no dependencies.

---

## 🌐 Live Demo

🔗 [View Live Site]((https://agent-69f2584035615ec8022d806b--alexandria-metro.netlify.app/)

---

## 📸 Preview

The site features a dark metro-themed design with electric blue accents, fully responsive
across mobile, tablet, and desktop. It supports both English (LTR) and Arabic (RTL) layouts
with a single click.

---

## 📋 Pages & Features

### 🏠 Home
- Animated hero section with live "under construction" badge
- Scrolling news ticker with latest project updates
- Project statistics (€1.3B investment, 20 stations, 60K passengers/hour)
- Quick access cards to all major sections
- Feature highlights grid
- News preview section
- Full footer with links, social media, and contact info

### 🗺 Trip Planner
- **BFS (Breadth-First Search) Algorithm** — finds the shortest path between any two stations
- **GPS Nearest Station Detection** — uses browser Geolocation API to find the closest station
- Visual step-by-step route display with departure/arrival markers
- Estimated travel time, distance (km), and number of stops
- Instant fare preview for Single and Return tickets
- Swap origin/destination button

### 🕐 Timetable
- Separate schedules for Weekdays, Friday, and Saturday–Sunday
- First and last train times per station
- Peak and off-peak frequency tables
- Service frequency breakdown (headway in minutes, trains per hour)

### 💳 Fares & Tickets
- **Interactive Fare Calculator** — calculates price based on BFS stop count
- Three ticket types: Single Journey, Return Ticket, 10-Trip Bundle
- Savings indicators for bundle tickets
- Travel Passes: Day Pass, Monthly Pass (most popular), Annual Pass
- Discount information: Disability (50%), Student (30%), Senior (40%), Children free

### 🚉 Station Guide
- All 20 stations displayed as cards
- Filter by: All / Ground Level / Elevated
- Live search by station name (English or Arabic)
- Each card shows: station type, facilities icons, km from Misr Station
- Bilingual station names (English + Arabic on each card)

### 🏗 Construction Progress
- Overall Phase 1 completion percentage (68%)
- Individual progress bars: Civil Works, Electrification, Station Fitout, Rolling Stock
- Full milestone timeline with status indicators (Done ✓ / Active ● / Pending ○)
- All 3 project phases overview with status badges

### 📰 News & Updates
- 6 real news articles about the project
- Covers: train manufacturing deal, civil works progress, financing, environmental impact

### 📞 Contact
- Full contact form with name, email, subject, and message fields
- Form validation with error messages in both languages
- Contact info: hotline, email, address, office hours
- Social media links

---

## 🛠 Tech Stack

| Technology | Details |
|---|---|
| HTML5 | Semantic structure, meta tags, Open Graph |
| CSS3 | CSS Variables, Grid, Flexbox, animations, RTL support |
| Vanilla JavaScript | No frameworks, no libraries |
| Google Fonts | Barlow Condensed, Barlow, Cairo (Arabic), JetBrains Mono |
| Browser APIs | Geolocation API (GPS), DOM API |
| Algorithm | BFS (Breadth-First Search) for shortest path routing |

**Total size:** ~124 KB — single `.html` file  
**Dependencies:** Zero (fonts load from Google Fonts CDN)  
**Build tools:** None required

---

## 🚀 Getting Started

### Option 1 — Open Directly (No GPS)
Just double-click `index.html` to open in your browser.  
Note: The GPS "Nearest Station" feature will not work on `file://` protocol.

### Option 2 — Local Server (Full Features including GPS)

**Using Python (recommended):**
```bash
# Python 3
python -m http.server 8080
```
Then open: [http://localhost:8080](http://localhost:8080)

**Using Node.js:**
```bash
npx serve .
```

**Using VS Code:**
Install the "Live Server" extension → Right-click `index.html` → Open with Live Server

---

## 📡 Why a Local Server for GPS?

The browser Geolocation API requires a **secure context** (HTTPS or localhost) to function.
Opening the file directly via `file://` blocks location access for security reasons.
Running it through any local server on `localhost` enables GPS features fully.

---

## 🌍 Bilingual Support

The site fully supports **English** and **Arabic** with a single toggle button.

| Feature | Details |
|---|---|
| Language Toggle | Top-right corner button |
| Arabic Font | Cairo (Google Fonts) — optimized for Arabic readability |
| RTL Layout | Full right-to-left layout switch including navigation, cards, forms |
| Translated Content | All text, labels, error messages, and placeholders |
| Number Formatting | Adapts to locale |

---

## 🗺 Station Data — Line 1 (All 20 Stations)

| # | English Name | Arabic Name | Type | km |
|---|---|---|---|---|
| S01 | Misr Station | محطة مصر | Ground | 0.0 |
| S02 | Sidi Gaber | سيدي جابر | Ground | 1.4 |
| S03 | Sporting | سبورتنج | Ground | 2.6 |
| S04 | Bab Sharq | باب شرق | Ground | 3.5 |
| S05 | Al-Zahriya | الزهرية | Ground | 4.4 |
| S06 | Al-Ibrahimiya | الإبراهيمية | Ground | 5.3 |
| S07 | Kafr Abdo | كفر عبده | Elevated | 6.1 |
| S08 | Victor Emanuel | فيكتور إيمانويل | Elevated | 6.9 |
| S09 | Touson | طوسون | Elevated | 7.7 |
| S10 | Glymenopoulo | جليمنوبولو | Elevated | 8.5 |
| S11 | Gabriel | جبريل | Elevated | 9.4 |
| S12 | Mandara | المندرة | Elevated | 10.8 |
| S13 | Asafra | العصافرة | Elevated | 12.1 |
| S14 | Abu Yousif | أبو يوسف | Elevated | 13.4 |
| S15 | Montaza | المنتزه | Elevated | 14.7 |
| S16 | Al-Nakheel | النخيل | Elevated | 15.8 |
| S17 | Maamoura | المعمورة | Elevated | 16.9 |
| S18 | Hannoville | هانوفيل | Elevated | 18.1 |
| S19 | New Abu Qir | أبو قير الجديدة | Elevated | 19.5 |
| S20 | Abu Qir | أبو قير | Elevated | 21.7 |

---

## 🔍 BFS Algorithm Explained

The Trip Planner uses **Breadth-First Search (BFS)** to find the shortest route between stations.

```
Graph: Linear bidirectional graph
Nodes: 20 stations (IDs 0–19)
Edges: Each station connects to its adjacent neighbors
       Station 0 ↔ 1 ↔ 2 ↔ ... ↔ 19

BFS guarantees the minimum number of stops between any two stations.
Time complexity:  O(V + E) where V=20, E=38
Space complexity: O(V)
```

Since Line 1 is a linear route, BFS always finds the unique shortest path.
The algorithm is already set up to scale for future branching lines (Phase 2, 3).

---

## 💰 Fare Calculation Logic

Fares are calculated dynamically based on the BFS stop count:

```
base_fare     = 5 EGP
per_stop_rate = 3 EGP
single_fare   = base_fare + (stops - 1) × per_stop_rate

return_fare   = single_fare × 1.8   (10% discount)
bundle_10     = single_fare × 10 × 0.8   (20% discount)
```

*Note: These are indicative fares based on planned pricing structure.*

---

## 🏗 Project Facts

| Detail | Value |
|---|---|
| Total Cost | €1.3 billion (~EGP 68 billion) |
| Line Length | 21.7 km (Phase 1) |
| Stations | 20 (6 ground-level, 14 elevated) |
| Trains | 21 trains, 189 railcars |
| Train Manufacturer | NERIC (East Port Said, Egypt) |
| Main Contractor | Orascom Construction + Colas Rail (France) |
| Client | National Authority for Tunnels (NAT) |
| Financing | EIB, EBRD, AFD, AIIB |
| Expected Opening | Q3 2026 |
| Capacity | 60,000 passengers/hour/direction |
| Travel Time | 25 min (vs 50 min previously) |
| Headway (peak) | 2.5 minutes |

---

## 📁 Project Structure

```
alexandria-metro/
│
└── alexandria-metro-v2.html          ← Entire website (HTML + CSS + JS)
└── README.md           ← This file
```

---



## 📄 License

This project is open source and available for educational and informational purposes.
Data sourced from public announcements by the National Authority for Tunnels (NAT),
Egyptian Ministry of Transport, and international development banks.

---

## 🤝 Contributing

Pull requests are welcome. For major changes, please open an issue first.

Areas where contributions are welcome:
- Real fare data once officially announced
- Additional station facilities information
- Phase 2 and Phase 3 station data
- Accessibility improvements
- PWA (Progressive Web App) manifest

---

## 📬 Contact

For questions about this project, open a GitHub Issue.  
For questions about the real Alexandria Metro, contact:

- **Hotline:** 08008000
- **Email:** info@alexmetro.eg
- **Authority:** National Authority for Tunnels (NAT), Egypt

---

*Built with ❤️ for Alexandria — عروس البحر المتوسط*
