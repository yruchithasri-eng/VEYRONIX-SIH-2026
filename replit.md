# VEYRONIX

VEYRONIX is a local-first smart medical-waste collection, AI segregation, trolley simulation, traceability, and compliance console for SIH 2026.

## Run & Operate

- `pnpm --filter @workspace/api-server run dev` — run the API server (port 5000)
- `pnpm --filter @workspace/veyronix run dev` — run the VEYRONIX web app
- `pnpm run typecheck` — full typecheck across all packages
- `pnpm run build` — typecheck + build all packages
- `pnpm --filter @workspace/api-spec run codegen` — regenerate API hooks and Zod schemas from the OpenAPI spec
- `pnpm --filter @workspace/db run push` — push DB schema changes (dev only)
- Required env: `DATABASE_URL` — Postgres connection string

## Stack

- pnpm workspaces, Node.js 24, TypeScript 5.9
- API: Express 5
- DB: PostgreSQL + Drizzle ORM
- Validation: Zod (`zod/v4`), `drizzle-zod`
- API codegen: Orval (from OpenAPI spec)
- Build: esbuild (CJS bundle)

## Where things live

- `artifacts/veyronix/src/App.tsx` — product shell, routes, local state, demo workflows, simulated GPS/AI, and page views
- `artifacts/veyronix/src/index.css` — VEYRONIX visual tokens, responsive layout helpers, motion, and print rules
- `artifacts/veyronix/.replit-artifact/artifact.toml` — managed web artifact metadata and preview routing
- `lib/api-spec/openapi.yaml` — shared API contract for the workspace; VEYRONIX does not require it for the local-first prototype

## Architecture decisions

- The first SIH prototype is frontend-only and uses centralized React state with localStorage persistence so the complete demo works without hardware, API keys, GPS permissions, or paid services.
- The app uses Asia/Kolkata for all operational timestamps and derives the displayed date/time from the browser clock rather than shipping a fixed current date.
- Demo controls update shared bin telemetry, activity, notifications, and audit-visible events; simulated AI and trolley movement are intended for a reliable live presentation.

## Product

- Role-aware login for Super Admin, Supervisor, Waste Collector, and Waste Management Officer
- Responsive operations dashboard with live clock, smart-bin telemetry, collection pipeline, alerts, and local event activity
- Smart bin QR handoff, AI segregation review, traceability chain, simulated trolley GPS route, hospital map, incident command, analytics, reports, devices, audit log, user management, and settings
- Light, dark, and system themes plus offline queue/sync affordances

## User preferences

- User requested a finished SIH 2026 prototype for PS SIH26115, not a generic admin template.
- Avoid external hardware, paid APIs, real GPS permissions, and external YOLO services; keep the demo local and functional.

## Gotchas

- The managed VEYRONIX web workflow supplies `PORT` and `BASE_PATH`; use the workflow for previews instead of running Vite manually.
- Keep operational locations in the five supported settings choices and keep timestamps in Asia/Kolkata.

## Pointers

- See the `pnpm-workspace` skill for workspace structure, TypeScript setup, and package details
