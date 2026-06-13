# Utility Usage Predictor

A single-page web app that estimates your annual electricity and gas costs, broken down month by month, based on your appliances and local utility rates.

## Features

- **3-step wizard** — Household setup → Appliances → Results
- **ZIP-based climate zones** — Automatically maps your ZIP code to one of 6 US climate zones (Hot/Tropical through Very Cold) to season-adjust usage estimates
- **OpenEI URDB integration** — Search and auto-load real utility rate plans by ZIP code (optional free API key from [openei.org](https://openei.org))
- **26 preset appliances** across 8 categories: HVAC, Water Heating, Kitchen, Laundry, Lighting, Entertainment, EV Charging, and Always-On devices
- **Monthly cost chart** — Stacked bar chart (Chart.js) showing electricity vs. gas costs per month
- **Appliance breakdown table** — Annual kWh, therms, and dollar cost per appliance with percentage share
- **Persistent state** — Saves your inputs to `localStorage` so your session survives a page refresh

## Usage

Open `index.html` directly in any modern browser — no build step or server required.

**Step 1 — Household Setup**
- Enter your 5-digit ZIP code (auto-detects climate zone)
- Set household size
- Enter electricity rate (¢/kWh) and fixed monthly fee, or search for your provider to load real rates
- Optionally enable gas and enter gas rate ($/therm) and fixed fee

**Step 2 — Appliances**
- Toggle the appliances you own on/off
- Adjust wattage/BTU, summer hours/day, winter hours/day, and quantity for each appliance

**Step 3 — Results**
- View annual total cost, peak month, and lowest month
- Inspect the monthly stacked bar chart
- See a ranked breakdown of cost by appliance

## No Installation

```
open index.html
```

No dependencies to install. Chart.js is loaded from CDN.

## Data Sources

- Climate zone seasonal factors are baked in (6 zones mapped from ZIP prefix ranges)
- Live utility rate data from the [OpenEI Utility Rate Database (URDB)](https://openei.org/wiki/Utility_Rate_Database) — requires a ZIP code entered in Step 1; a free API key removes rate limits
