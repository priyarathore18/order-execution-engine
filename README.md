
# Order Execution Engine (Mock) - Deliverables Bundle

This repository is a prepared deliverables package for the **Order Execution Engine** assignment. It contains the API, WebSocket updates, mock DEX routing (Raydium & Meteora), queueing with BullMQ, PostgreSQL schema, tests, Postman collection, Docker Compose, and demo recording script.

## Quickstart (local)

1. Copy `.env.example` to `.env` and set values (Postgres + Redis)
2. Start services (Docker):
   ```sh
   docker-compose up -d
   ```
3. Install dependencies:
   ```sh
   npm install
   ```
4. Start in dev:
   ```sh
   npm run dev
   ```

## Tests
```sh
npm test
```

## Design decisions (short)
- Implemented **Market Order** (immediate execution) as mock engine for deterministic testing.
- DEX routing simulates Raydium vs Meteora prices (2-5% variation) with realistic delays.
- Single endpoint `/api/orders/execute` accepts POST and upgrades same connection to WebSocket for live status streaming.
- BullMQ is used for reliable queueing, with up to 10 concurrent workers and exponential backoff retries (≤3).

## Deploy & Video
This bundle includes a demo script (`DEMO_SCRIPT.md`) describing the 1-2 minute video steps and exact commands to run multiple orders and capture WebSocket output.
