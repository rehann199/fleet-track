# Fleet-Track: Engineering Notes

An honest summary of the design problems this project addresses and where each is implemented. Items marked *backend (reference)* exist as code in the unused backend and were not exercised in the demo; no performance or scale figures are claimed.

## 1. One workspace for map, deliveries, fleet and analytics
Dispatchers normally jump between tools. The SPA keeps all five views in one page with hash navigation and lazily initialized sections (the map is resized and fitted to markers when its tab becomes visible; charts render on first visit to Analytics). *Implemented in the frontend.*

## 2. A demo that works without infrastructure
The UI is driven by mock data providers with relative timestamps so ETAs always look current. This allows the full interface to be reviewed without a database. The trade-off is that nothing persists and no live updates occur. *Implemented in the frontend.*

## 3. Scoped real-time updates
The backend uses one Socket.IO room per delivery (`delivery-<id>`) so location updates are only sent to clients tracking that delivery. *Backend (reference); not connected to the UI.*

## 4. Role-based access
JWT middleware checks the user's role per route, and a helper allows access to a resource for its owner or for admin/manager roles. *Backend (reference).*

## 5. Route ordering with a fallback
`routeService` uses an external directions API only when a key is configured; otherwise it orders stops with a haversine nearest-neighbor pass. This is a simple heuristic, not an optimizer or ML. *Backend (reference).*

## 6. Optional integrations fail soft
SMS and routing services check for credentials and disable themselves when absent instead of crashing the app. *Backend (reference).*

## 7. Basic API protection
helmet headers and a per-IP rate limit on `/api/` are configured. *Backend (reference).*

## 8. Tests and packaging
Jest and Cypress are configured, with a single API test file; Docker/compose files describe PostgreSQL, Redis and the app. These were not run as part of the portfolio build.
