# Fleet-Track: Privacy and Source

## Source Code Status

The full source code for Fleet-Track is not included in this portfolio repository. This repository contains architecture documentation, screenshots and UI documentation. The demo frontend runs on hardcoded mock data and needs no backend.

## Demo Data

All screenshots and live examples shown in the portfolio use fictional, seeded demonstration data. This includes:

- Mock vehicles, drivers, and delivery locations (non-real addresses)
- Fictional customer names and phone numbers
- Synthetic GPS coordinates and delivery histories
- Example analytics and performance metrics

No real customer, driver or operational data appears in any documentation or screenshot.

## Secrets and Configuration

The portfolio excludes all sensitive configuration:

- Database credentials and connection strings
- Twilio API keys and phone numbers
- JWT signing keys
- Cloud service credentials
- Third-party API tokens
- Internal IP addresses, ports, and hostnames

Environment files (.env, .env.local) are not included. 

## Backend Availability

The backend is a reference implementation and was not runnable as shipped (see ARCHITECTURE.md). It documents:

- The data model (Sequelize definitions)
- API route structure and authentication middleware
- Real-time Socket.IO room patterns
- Integration with Twilio and route services
- Docker Compose deployment configuration

Running the backend requires external services (PostgreSQL, Twilio credentials) that are intentionally not configured in the portfolio.

## Third-Party Licenses

The project depends on several open-source and third-party services:

- **Leaflet** and **OpenStreetMap** for mapping (open-source)
- **Chart.js** for analytics visualization (MIT license)
- **Socket.IO** for real-time communication (MIT license)
- **Express**, **Node.js**, **Sequelize**, and **PostgreSQL** (respective open-source licenses)
- **Twilio** SMS service (commercial API; credentials excluded)
- **Font Awesome** icons (via CDN; commercial usage licenses apply)

All third-party names and trademarks remain the property of their respective owners.

## Access and Reuse

- **Permitted:** Read and link to documentation, screenshots, and UI descriptions for evaluation and reference.
- **Not permitted:** Copy, redistribute, or reuse code, diagrams, screenshots, or proprietary assets without explicit permission.

This portfolio is provided for hiring, evaluation, and portfolio review only.
