# ScalpX Pro — Mobile Forex Scalping Robot (Working Title)

Short description
ScalpX Pro is a mobile-first control app for a high-speed, risk-managed Forex scalping robot. The trading logic runs on a VPS or connected MT4/MT5 terminal (Expert Advisor). The mobile app provides monitoring, control and basic analytics while the EA executes trades with strict capital preservation rules.

Vision
Protect small accounts (cent accounts), enable disciplined scalping with automated risk-control, and provide an easy-to-use mobile control surface for traders of all levels.

Core features
- Precision entries with multi-layer confirmation (market structure, volatility, spread, momentum)
- Adjustable risk per trade (0.1%–2%) and automatic lot-sizing
- Max trades/day, max drawdown and daily loss limits (auto-stop)
- Dashboard: balance, equity, open trades, daily P/L, win rate, drawdown
- Controls: Start/Stop, Risk Mode (Aggressive/Balanced/Safe), Trading Sessions, Read-only mode
- Logs: trade history, entry/exit reasons
- Secure encrypted API bridge between mobile app and trading engine

Supported instruments & timeframes
- Forex majors & selected minors: EURUSD, GBPUSD, USDJPY, (XAUUSD optional)
- Timeframes: M1 primary, M5 confirmation

Architecture overview
- Trading engine: MT4/MT5 EA (MQL4/MQL5) running on a VPS or trader's terminal
- Mobile: React Native or Flutter app for iOS/Android (control & monitoring)
- Backend bridge: secure REST/WebSocket API to relay signals, metrics, and commands
- Security: encrypted transport (TLS), no broker passwords stored in app, read-only mode option

Getting started (developer)
1. Choose target EA platform: MT4 (MQL4) or MT5 (MQL5).
2. Build EA scaffolding with:
   - risk manager (dynamic lot sizing)
   - entry/exit rules module
   - trade limiter and safety module (drawdown/daily loss)
   - logging + HTTP client (or socket) to post events to the bridge
3. Implement bridge service with authentication and encryption.
4. Build mobile UI for monitoring and control + push notifications for critical events.

Suggested tech stack
- EA: MQL4 / MQL5 (Expert Advisor)
- Backend bridge: Node.js (Express/Fastify) or Go (Gin) — supports REST and WebSocket
- Mobile app: React Native (Expo) or Flutter
- Database: PostgreSQL (production) / SQLite for light usage
- Hosting: VPS for EA; cloud (Heroku/Render/AWS) for bridge if public access required
- CI/CD: GitHub Actions

Security & compliance
- Store no broker passwords on the server or app unless strictly encrypted; prefer an external manual connector.
- Use TLS, JWT or mutual TLS for API authentication.
- Provide explicit risk disclaimer on first app run and before enabling live trading.

License & contribution
- Add license when ready (MIT/Proprietary license options)
- Include contributor guidelines and code of conduct for external contributors

Contact
- Repository owner / maintainer: deep1hacker
