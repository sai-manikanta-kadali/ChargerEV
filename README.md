# ChargeNear — Community EV Charging & Emergency Assistance

ChargeNear is an India-focused peer-to-peer EV charging network prototype. It explores how EV drivers could discover nearby community charging hosts, estimate charging costs, request emergency or scheduled charging, and learn about connector and electrical safety.

## Product capabilities

- **Driver discovery:** Map-based host discovery, city and connector filters, distance sorting, and booking requests.
- **Host onboarding:** Submit a listing with equipment, connectors, availability, tariff, and safety declarations.
- **Administration:** Review host applications and manage safety reports.
- **EV help tutor:** Gemini-backed responses with a deterministic educational fallback.
- **Charging calculator:** Estimate energy required, time, cost, and approximate range added.
- **Location privacy:** Public host coordinates are obfuscated; exact addresses are intended to be disclosed only in accepted/completed booking flows.

## Technology

| Area | Tools |
|---|---|
| Frontend | React, TypeScript, Vite, Tailwind CSS |
| Backend | Node.js, Express, TypeScript |
| AI | Google Gemini API |
| Maps | Leaflet, OpenStreetMap |
| Tests | Node test runner, TypeScript |

## Run locally

Requirements: Node.js compatible with the dependencies in `package.json`.

```bash
git clone https://github.com/sai-manikanta-kadali/ChargerEV.git
cd ChargerEV
npm install
```

Create a local `.env` file based on `.env.example` and set `GEMINI_API_KEY` if you want Gemini-powered tutor responses. Keep API keys out of Git.

```bash
npm run dev
```

Build, type-check, and test:

```bash
npm run build
npm run lint
npm test
```

## Repository map

- `src/App.tsx` — main application state and navigation
- `src/components/` — driver, host, admin, booking, map, and AI tutor views
- `src/utils/chargingLogic.ts` — distance, charging estimates, privacy helpers, validation, and fallback tutor logic
- `src/utils/chargingLogic.test.ts` — automated unit tests
- `server.ts` — Express API and local JSON persistence

## Prototype limitations and safety

- This is a learning/prototype project, not a production charging marketplace.
- Bundled host, user, and booking records include demo/sample data. They are not verified real charging stations.
- The current server uses a local JSON file for persistence; production needs durable database storage and backups.
- Authentication and role handling are prototype-level. Production requires verified identity, server-enforced authorization, and secure session management.
- Electrical safety declarations and charging estimates are informational only. Actual installation, earthing, RCCB protection, connector compatibility, and charging time must be verified by qualified professionals and equipment documentation.
- Never treat a demo listing as an available or safety-certified charger.

## Roadmap

- Add verified authentication and role-based authorization.
- Replace local JSON persistence with a managed database.
- Add host verification and audit trails.
- Expand integration tests for booking and privacy workflows.
- Add deployment monitoring and a production security review.

---

Built to explore full-stack product engineering, maps, API design, and AI-assisted user support.