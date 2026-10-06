# Fleet-Track: Product Overview

## What It Is

Fleet-Track is a courier and fleet management dashboard concept. It gives dispatchers a map of vehicles and deliveries, delivery status monitoring, vehicle and driver cards, and analytics in a single-page interface. In this portfolio build it runs on fictional mock data.

## Core Features

**Dashboard & Monitoring**
- Map showing vehicle and delivery locations with markers and route lines (positions come from mock data)
- Delivery table with status and priority badges and status/search filters
- Vehicle and driver cards displaying utilization, status and contact details
- KPI cards: active vehicles, pending deliveries, completed today, average delivery time

**Tracking & Communication**
- Backend (reference, not connected to the UI): Socket.IO position updates and Twilio SMS ETA notifications
- Delivery route visualization on the map
- Driver assignment and vehicle assignment workflows

**Analytics**
- Charts: weekly delivery volume vs on-time, vehicle utilization, route efficiency (mock numbers)

## User Interface

The frontend is a single-page application built with vanilla JavaScript, Leaflet (for mapping) and Chart.js (for analytics). It uses OpenStreetMap tiles for background maps and Font Awesome icons for UI polish. The interface is optimized for desktop use in dispatch centers.

## Architecture: Frontend & Backend

The **frontend** (public/) runs entirely client-side; the portfolio includes a demo build with hardcoded mock data so it works without a backend server.

The **backend** (not runnable as shipped) is a Node.js/Express server with:
- PostgreSQL database and Sequelize ORM for persistence
- JWT-based role authentication (roles: admin, dispatcher, driver)
- REST API and Socket.IO rooms for real-time delivery updates
- Rate limiting and Helmet headers
- Integration with external services (Twilio for SMS, route optimization)

A production backend would handle live vehicle tracking, driver authentication, delivery assignment and persistence, while the frontend would consume that API in place of demo data.

## Data & Demo Mode

The portfolio demo builds from seeded fictional data embedded in the frontend. No backend server or database is required to view the interface. This is noted clearly to evaluators.
