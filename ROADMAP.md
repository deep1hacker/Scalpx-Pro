# Roadmap — ScalpX Pro

Goal
Deliver an MVP that allows mobile control/monitoring of a safe, automated Forex scalping EA running on MT4/MT5 with basic risk protections and logging.

Milestone M0 — Planning & repo setup (0–1 week)
- Finalize EA target: MT4 or MT5
- Choose mobile framework (React Native or Flutter)
- Create repo structure, README, CONTRIBUTING, LICENSE, ISSUE templates (this commit)
- Create core labels and milestones

Milestone M1 — EA core & safety (2–4 weeks)
- Implement trading engine skeleton in MQL4/5:
  - risk manager: dynamic lot calculation by % of equity
  - trade safety: max drawdown, daily loss limit, max trades/day, equity protection mode
  - entry/exit hook interfaces and logger
- Unit testing of risk calculations (offline)
- Local testing on demo account

Milestone M2 — Bridge & API (1–2 weeks)
- Implement secure bridge (REST + WebSocket) for telemetry and commands
- Authentication (JWT or mTLS), encrypted transport (TLS)
- Basic endpoints:
  - GET /status
  - POST /command { start | stop | setRisk | setMode }
  - WebSocket for real-time events and logs

Milestone M3 — Mobile control UI (2–4 weeks)
- Dashboard: balance, equity, open trades, P/L, drawdown
- Controls: Start/Stop, risk slider, mode selector, session selector
- Notifications: trade open/close, stop triggers, critical errors
- Demo mode with simulated trades

Milestone M4 — Testing, performance, and optimization (2–4 weeks)
- Stress test execution latency
- Backtest/forward test strategy on demo accounts
- Add spread & volatility filtering, news filter toggle
- Implement analytics: win-rate, avg trade time

Milestone M5 — Beta & Monetization (2–4 weeks)
- Create demo mode limits and subscription gating for premium features
- Prepare legal + risk disclaimer flow
- Onboard beta testers, gather feedback, iterate

Key success metrics for MVP
- EA stops automatically when drawdown/daily loss limit hit
- Lot-sizing computed correctly by percentage with cent account accuracy
- Mobile shows near-real-time trade events (<= 1–3s via WebSocket)
- Basic test results demonstrate positive risk-management behavior (not profit guarantee)

Issues & tasks (examples to create)
- [ ] Setup repo skeleton and CI
- [ ] Implement EA: risk manager module
- [ ] Implement EA: entry/exit signal module (stubs)
- [ ] Implement bridge: auth + TLS
- [ ] Mobile: implement dashboard skeleton
- [ ] Add logging and persistent trade history
- [ ] Add demo/simulated trade mode for mobile

Notes
- Prioritize safety and deterministic behavior over aggressive profit-seeking.
- Keep the core logic transparent and well-logged for debugging and regulatory clarity.
