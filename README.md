# HDB Resale Lookup

Search Singapore HDB resale flat transactions by town name or postal code. Data from the Singapore Government's open data portal (data.gov.sg).

## Features

- 🔍 **Dual search** — search by HDB town name or postal code
- 📊 **Live + fallback data** — uses data.gov.sg API with bundled historical data for reliability
- 🏷️ **Flat type filter** — filter by 1-Room, 2-Room, 3-Room, 4-Room, 5-Room, Executive, Multi-Generation
- 📈 **Sort options** — newest/oldest, price high/low, floor area largest/smallest
- 📉 **Stats panel** — count, average price, median price, $/sqm
- 📥 **CSV export** — download full transaction history for any town
- 📅 **12-month window** — shows recent transactions (configurable)
- 📱 **Responsive UI** — works on mobile and desktop

## Quick Start

```bash
pip install flask requests
python app.py
```

Open **http://localhost:5000** in your browser.

## Usage

1. **Select search mode** — Town or Postal Code
2. **Choose town** or enter a 6-digit postal code (e.g. `520123`)
3. **Filter by flat type** (optional, defaults to all types)
4. **Sort results** (default: newest first)
5. **Click Search** — results load with stats summary
6. **Download CSV** — click the CSV button to export all results

## Tech Stack

- Python 3.10 + Flask
- Bootstrap 5.3 (CDN)
- Pillow + Requests
- Singapore Government Open Data API

## Data Coverage

- ✅ All **27 HDB towns**
- ✅ **12 months** of transactions
- ✅ Bundled **fallback dataset** (~300 records) when API is unavailable
- ✅ Real resale prices, floor areas, storey ranges, lease info

## API Endpoints

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/` | GET | Main web UI |
| `/search` | POST | Search transactions |
| `/towns` | GET | List all 27 HDB towns |
| `/download?town=<name>` | GET | Export CSV |

## License

MIT