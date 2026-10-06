# Fleet-Track: Technical Case Study

## Problem
Logistics coordinators want vehicles, deliveries, drivers and performance numbers in one view instead of separate screens.

## What was built
- **Frontend (runs in the demo):** a vanilla JavaScript single-page app with a Leaflet map (vehicle and delivery markers, route lines, layer toggles), a deliveries table with status/priority badges and filters, vehicle and driver cards, and Chart.js analytics. All data comes from fictional mock providers in the browser.
- **Backend (reference, not wired to the UI):** Express + Sequelize/PostgreSQL models and REST routes, JWT role middleware, Socket.IO delivery rooms, a Twilio SMS service and a route service with a nearest-neighbor fallback. Not runnable as shipped.

## Key decisions
- **Vanilla JS, no framework:** the UI is mostly data display; keeping dependencies to Leaflet, Chart.js and Font Awesome keeps it simple.
- **Relational model:** vehicles, drivers, customers, deliveries, routes and tracking updates are modeled with Sequelize.
- **Per-delivery Socket.IO rooms** to scope live updates (reference backend only).
- **Heuristic routing:** nearest-neighbor ordering; no ML or solver.
- **Mock-first demo:** allows review without PostgreSQL or credentials.

## Demo adjustments made for this portfolio
1. Charts render when Analytics opens (the chart manager was previously never invoked).
2. Average delivery time shows hours with one decimal (previously rounded days, always "0").
3. Map is resized and fitted to markers after load to avoid partial tiles.
4. A UI polish layer (design tokens, Inter font, styling, favicon/logo mark) and enriched fictional mock data.

## Limitations
- No live data, persistence or authentication in the running UI.
- Backend needs repairs plus PostgreSQL to run; real-time tracking, SMS and analytics aggregation were never exercised in this build.
- Requires internet for map tiles and CDN assets.
