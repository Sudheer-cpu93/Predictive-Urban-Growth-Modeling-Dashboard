UrbanPulse — Predictive Urban Growth Modeling Dashboard
> **Problem Statement 3** — Predictive Urban Growth Modeling for Real Estate Investment  
> Submitted to: Sashrik@cyberjoar.com | CyberJoar Technologies
---
Overview
UrbanPulse is a fully client-side, AI-powered web dashboard that identifies future real estate "hotspots" by fusing municipal intelligence, market data, pricing velocity, and rental absorption signals into a single Growth Velocity Score (GVS) per zone.
The system supports any Indian city — either entered manually or detected automatically via GPS — and generates a live, AI-researched analysis using Claude's web search capability.
---
Features
Feature	Description
Location Detection	GPS-based current location OR manual city entry with autocomplete
AI Scrape Engine	Calls Claude API + live web search to pull real municipal & market data
Geospatial Heatmap	Interactive SVG map with hover tooltips showing ₹/sqft, yield, trend
Growth Velocity Ranking	All zones ranked by composite GVS score out of 100
Trend Charts	Price velocity, radar factor breakdown, rental yield vs growth bubble chart
ROI Calculator	Sliders for amount, horizon, property type — live CAGR & returns projection
Risk Assessment Matrix	6-factor risk scoring per city
PDF Export	One-click professional report download
Dark Mode	Automatic system-level dark/light theme support
---
How to Run
Download `UrbanPulse_v3_LocationAware.html`
Open it in any modern browser (Chrome, Firefox, Edge)
No server required — runs entirely in the browser
Allow location permission or type any city name manually
Click Analyze and wait ~5 seconds for the AI to generate the dashboard
> **Note:** The AI Scrape Engine requires an active internet connection to call the Claude API with web search. All other features (charts, ROI calculator, PDF export) work fully offline.
---
Architecture
```
User Input (GPS / Manual City)
        │
        ▼
Nominatim Reverse Geocoder (OpenStreetMap)
        │
        ▼
Claude API  ──── web_search tool ────►  Municipal portals
(claude-sonnet-4-20250514)              99acres / MagicBricks
        │                               Punjab PWD / LMC
        ▼
Structured JSON Response
{zones, scores, feed, risks, summary}
        │
        ▼
Dashboard Render
├── SVG Heatmap (D3-style manual SVG)
├── Chart.js (Line, Radar, Bubble, Bar)
├── ROI Calculator (JS math model)
└── jsPDF (PDF export)
```
---
Growth Velocity Score Formula
```
GVS = (Municipal Declarations  × 0.35)
    + (Market Listing Density  × 0.25)
    + (Pricing Velocity        × 0.25)
    + (Rental Absorption       × 0.15)

Infrastructure Trigger Bonus  → +8 pts
CLU Policy Change             → +5 pts
```
Why this weighting?  
Municipal declarations are the strongest lead indicator — government budget allocations and tenders precede price appreciation by 12–24 months. Market and pricing signals act as demand confirmation. Rental absorption reveals actual population movement into a zone.
---
Data Sources
Stream	Source Type	Analytical Value
Municipal Declarations	Government Portals / AI Web Search	Anticipates new roads, utilities, transport hubs
Listing Density	99acres / MagicBricks (via AI search)	Measures developer activity & competition saturation
Pricing Velocity	Real Estate Portals (via AI search)	Tracks rate of appreciation (Ready-to-Move vs Under-Construction)
Rental Absorption	Online Portals (via AI search)	Indicates residency demand and population shift
---
Tech Stack
Component	Technology
Frontend	Vanilla HTML5 / CSS3 / JavaScript (no framework)
Charts	Chart.js 4.4.1
PDF Export	jsPDF 2.5.1
AI Engine	Claude API (`claude-sonnet-4-20250514`) + `web_search_20250305` tool
Geocoding	OpenStreetMap Nominatim (free, no API key)
Fonts	Google Fonts — Syne + Space Mono
---
File Structure
```
UrbanPulse_v3_LocationAware.html   ← Main application (single file, no dependencies)
README.md                           ← This file
UrbanPulse_Ludhiana.html            ← Ludhiana-specific static version (v2)
```
---
Tested Cities
City	Zones Generated	Top Zone	Notes
Ludhiana, Punjab	12	Aerocity Road	Infra trigger: LMC ₹340Cr sewage project
Chandigarh	8–10	Sector 17 / IT Park	High municipal activity
Delhi NCR	10+	Dwarka Expressway	Metro expansion signals
Mumbai	10+	Thane / Navi Mumbai	Infrastructure-heavy
---
Logic Summary (for submission email)
The core insight behind UrbanPulse is that government declarations are a leading indicator of real estate appreciation — they precede price growth by 12–24 months. By fusing municipal tender data with live market signals from real estate portals, the system computes a forward-looking Growth Velocity Score rather than relying on lagging historical prices.
The AI layer (Claude + web search) automates the data scraping pipeline that would otherwise require manual collection from multiple portals. The result is a unified, interactive dashboard that lets analysts instantly visualize where development will accelerate over a 24–60 month horizon — for any Indian city.
---
Author
Submitted as part of the hiring assignment for CyberJoar Technologies.  
Built using: Claude AI (Anthropic), Chart.js, jsPDF, Vanilla JS.
---
UrbanPulse v3.0 — Predictive Urban Growth Modeling for Real Estate Investment
