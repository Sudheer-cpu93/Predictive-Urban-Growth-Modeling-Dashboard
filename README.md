UrbanPulse — Predictive Urban Growth Modeling Dashboard

Problem Statement 3 — Predictive Urban Growth Modeling for Real Estate Investment
Submitted to: Sashrik@cyberjoar.com | CyberJoar Technologies


Overview
UrbanPulse is a fully client-side, AI-powered web dashboard that identifies future real estate "hotspots" by fusing municipal intelligence, market data, pricing velocity, and rental absorption signals into a single Growth Velocity Score (GVS) per zone.
The system supports any Indian city — either entered manually or detected automatically via GPS — and generates a live, AI-researched analysis using Claude's web search capability.

Features
FeatureDescriptionLocation DetectionGPS-based current location OR manual city entry with autocompleteAI Scrape EngineCalls Claude API + live web search to pull real municipal & market dataGeospatial HeatmapInteractive SVG map with hover tooltips showing ₹/sqft, yield, trendGrowth Velocity RankingAll zones ranked by composite GVS score out of 100Trend ChartsPrice velocity, radar factor breakdown, rental yield vs growth bubble chartROI CalculatorSliders for amount, horizon, property type — live CAGR & returns projectionRisk Assessment Matrix6-factor risk scoring per cityPDF ExportOne-click professional report downloadDark ModeAutomatic system-level dark/light theme support

How to Run

Download UrbanPulse_v3_LocationAware.html
Open it in any modern browser (Chrome, Firefox, Edge)
No server required — runs entirely in the browser
Allow location permission or type any city name manually
Click Analyze and wait ~5 seconds for the AI to generate the dashboard


Note: The AI Scrape Engine requires an active internet connection to call the Claude API with web search. All other features (charts, ROI calculator, PDF export) work fully offline.


Architecture
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

Growth Velocity Score Formula
GVS = (Municipal Declarations  × 0.35)
    + (Market Listing Density  × 0.25)
    + (Pricing Velocity        × 0.25)
    + (Rental Absorption       × 0.15)

Infrastructure Trigger Bonus  → +8 pts
CLU Policy Change             → +5 pts
Why this weighting?
Municipal declarations are the strongest lead indicator — government budget allocations and tenders precede price appreciation by 12–24 months. Market and pricing signals act as demand confirmation. Rental absorption reveals actual population movement into a zone.

Data Sources
StreamSource TypeAnalytical ValueMunicipal DeclarationsGovernment Portals / AI Web SearchAnticipates new roads, utilities, transport hubsListing Density99acres / MagicBricks (via AI search)Measures developer activity & competition saturationPricing VelocityReal Estate Portals (via AI search)Tracks rate of appreciation (Ready-to-Move vs Under-Construction)Rental AbsorptionOnline Portals (via AI search)Indicates residency demand and population shift

Tech Stack
ComponentTechnologyFrontendVanilla HTML5 / CSS3 / JavaScript (no framework)ChartsChart.js 4.4.1PDF ExportjsPDF 2.5.1AI EngineClaude API (claude-sonnet-4-20250514) + web_search_20250305 toolGeocodingOpenStreetMap Nominatim (free, no API key)FontsGoogle Fonts — Syne + Space Mono

File Structure
UrbanPulse_v3_LocationAware.html   ← Main application (single file, no dependencies)
README.md                           ← This file
UrbanPulse_Ludhiana.html            ← Ludhiana-specific static version (v2)

Tested Cities
CityZones GeneratedTop ZoneNotesLudhiana, Punjab12Aerocity RoadInfra trigger: LMC ₹340Cr sewage projectChandigarh8–10Sector 17 / IT ParkHigh municipal activityDelhi NCR10+Dwarka ExpresswayMetro expansion signalsMumbai10+Thane / Navi MumbaiInfrastructure-heavy

Logic Summary (for submission email)
The core insight behind UrbanPulse is that government declarations are a leading indicator of real estate appreciation — they precede price growth by 12–24 months. By fusing municipal tender data with live market signals from real estate portals, the system computes a forward-looking Growth Velocity Score rather than relying on lagging historical prices.
The AI layer (Claude + web search) automates the data scraping pipeline that would otherwise require manual collection from multiple portals. The result is a unified, interactive dashboard that lets analysts instantly visualize where development will accelerate over a 24–60 month horizon — for any Indian city.

Author
Submitted as part of the hiring assignment for CyberJoar Technologies.
Built using: Claude AI (Anthropic), Chart.js, jsPDF, Vanilla JS.

UrbanPulse v3.0 — Predictive Urban Growth Modeling for Real Estate Investment
