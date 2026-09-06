# AgosLens PH

AgosLens PH is a responsive Philippine flood-potential and river-conditions
explorer built with Next.js, TypeScript, Tailwind CSS, Leaflet, and Recharts.

It combines public environmental APIs to provide:

- Philippine city and municipality search
- A Philippines-centered interactive map
- Live indicators for 18 representative locations
- Recent RainViewer radar animation
- Optional NASA GIBS satellite-precipitation imagery
- NASA EONET flood and severe-storm events
- Open-Meteo rainfall forecasts
- Open-Meteo river-discharge forecasts
- Explainable project-defined flood-potential levels
- Loading, offline, empty, missing-data, and independent error states
- A two-location comparison laboratory
- A methodology and data-sources page

## Important wording

AgosLens PH shows forecast-based environmental indicators. It does not confirm
current street flooding and does not replace PAGASA or local government
advisories.

## Requirements

- Node.js 20.9 or newer
- npm

## Run locally

```bash
npm install
npm run dev
```

Open `http://localhost:3000` in your browser.

## Production build

```bash
npm run build
npm start
```

The repository can be imported into Vercel as a standard Next.js application.

## Main routes

- `/` — centered map dashboard
- `/explorer` — dashboard plus two-location comparison
- `/methodology` — scoring rules, limitations, safeguards, and sources

## API services

- Open-Meteo Geocoding API
- Open-Meteo Forecast API
- Open-Meteo Flood API
- RainViewer Weather Maps API
- NASA EONET API
- NASA GIBS
- OpenStreetMap tiles

No API key or application database is required for the current version.

## Project structure

```text
app/
  page.tsx
  explorer/page.tsx
  methodology/page.tsx
components/
  comparison-lab.tsx
  data-charts.tsx
  flood-map.tsx
  flood-workspace.tsx
  location-search.tsx
  site-header.tsx
lib/
  agoslens.ts
```

## Potential calculation

The application adds project-defined points for forecast rainfall, increasing
river discharge, and current precipitation. The total is classified as Low,
Guarded, Elevated, or High. These categories are explained on the Methodology
page and are not official warning levels.
