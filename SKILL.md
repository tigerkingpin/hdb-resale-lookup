# HDB Transaction Lookup Web App

## 1. Project Overview
- **Type**: Flask web application
- **Core functionality**: User enters a Singapore postal code / HDB estate, app fetches HDB resale transactions from the last 12 months and displays them in a clean table
- **Target users**: Home buyers, property agents, researchers looking for HDB resale data

## 2. Tech Stack
- Flask (Python backend)
- HTML/CSS (frontend)
- OneMap Search API (postal code → lat/lon/town)
- HDB Resale Price Index data via data.gov.sg API (or OneMap transaction API)
- Bootstrap 5 (CDN) for responsive UI

## 3. Data Sources
- **OneMap API**: `https://www.onemap.gov.sg/api/common/elastic/search` — convert postal code to town/lat/lon
- **HDB Resale transactions**: `https://data.gov.sg` offers monthly HDB resale price data in JSON/CSV
- **Fallback**: If API is unavailable, use bundled sample data for demo

## 4. Features
- Search by postal code OR town name
- Display: Town, Block, Street Name, Flat Type, Storey, Floor Area (sqm), Resale Price, Price Per SQM, Month
- Filter by flat type (1-ROOM, 2-ROOM, 3-ROOM, 4-ROOM, 5-ROOM, EXECUTIVE, MULTI-GENERATION)
- Sort by date (default: newest first), price, floor area
- Export to CSV
- Mobile responsive

## 5. App Structure
```
hdb-transaction-app/
├── app.py              # Flask routes + data fetching logic
├── templates/
│   └── index.html      # Main UI
└── static/
    └── style.css       # Custom styles
```

## 6. API Endpoints
- `GET /` — Render search form
- `POST /search` — Accept postal code/town, return transactions as JSON
- `GET /download?town=X` — Download filtered results as CSV