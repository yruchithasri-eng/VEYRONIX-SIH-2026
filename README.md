# VEYRONIX — SIH 2026

VEYRONIX is a local-first smart medical-waste collection, AI-assisted segregation, trolley tracking, traceability, and compliance console built for **Smart India Hackathon 2026 · PS SIH26115**.

## Live app

**https://veyronix-sih-2026--ruchithayanagan.replit.app**

Demo access:

- **Email:** `admin@veyronix.com`
- **Password:** Any password

## What it demonstrates

- Smart-bin telemetry with fill level, temperature, battery, and sensor health
- Color-coded biomedical waste segregation for infectious, contaminated, sharps, glass/metal, and general waste
- AI detection simulation with confidence review and human verification
- Collection scheduling, QR handoff, custody traceability, and audit events
- Trolley route simulation with GPS movement, pause, stop, reset, and GPS failure/recovery controls
- Hospital map with departments, storage, collection points, and trolley status
- Alerts, incidents, emergency mode, notifications, and acknowledgement workflows
- Analytics, waste distribution, compliance reporting, CSV export, and print-ready reports
- Device and sensor health monitoring
- Role-aware access for Super Admin, Supervisor, Waste Collector, and Waste Management Officer
- Offline queue and local synchronization affordances
- Responsive PWA layout for desktop, tablet, and mobile

## Product direction

VEYRONIX is intentionally designed as a reliable SIH demonstration system:

- No external hardware is required
- No paid APIs or API keys are required
- GPS, AI vision, sensor telemetry, and route movement are simulated locally
- Operational timestamps use the Asia/Kolkata timezone
- Demo state persists in browser local storage

## Run locally

Requirements:

- Node.js 24+
- pnpm

Install dependencies and start the web app:

```bash
pnpm install
pnpm --filter @workspace/veyronix run dev
```

The application uses the `PORT` and `BASE_PATH` values supplied by the Replit workflow. For a production build:

```bash
PORT=20683 BASE_PATH=/ pnpm --filter @workspace/veyronix run build
```

Useful checks:

```bash
pnpm --filter @workspace/veyronix run typecheck
pnpm --filter @workspace/veyronix run build
```

## Project structure

- `artifacts/veyronix/src/App.tsx` — product shell, routes, shared local state, simulated workflows, and page views
- `artifacts/veyronix/src/index.css` — visual tokens, responsive helpers, motion, and print rules
- `artifacts/veyronix/public/manifest.webmanifest` — installable PWA metadata
- `artifacts/veyronix/public/sw.js` — local-first service worker
- `artifacts/veyronix/.replit-artifact/artifact.toml` — managed web artifact and deployment configuration

## Technology

- React
- TypeScript
- Vite
- Tailwind CSS
- Wouter
- Lucide React
- pnpm workspace

## SIH context

The system is designed to make biomedical waste movement visible and accountable from smart-bin collection through segregation, trolley movement, storage handoff, reporting, and audit review.