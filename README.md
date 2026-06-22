# SmartStudentHub

## Quick start ⚡

1. Copy `.env.example` to `.env` and fill values (e.g. `MONGO_URI`, `JWT_SECRET`).
2. Install dependencies:
   - npm install
   - (optional) cd backend && npm install
3. Start dev environment (backend + web):
   - npm run dev
4. To include mobile (Flutter) in dev run:
   - npm run dev:all

Convenience scripts (cross-platform):
- PowerShell: `.\scripts\run-all.ps1` — starts backend + web. Add `mobile` to include the Flutter app: `.\scripts\run-all.ps1 mobile`.
- Bash/Unix: `sh ./scripts/run-all.sh` — starts backend + web; pass `mobile` to include Flutter: `sh ./scripts/run-all.sh mobile`.
- NPM wrapper: `npm run run-all:sh` runs the Bash wrapper.

Notes:
- The backend uses `server.js` at project root as the entry point.
- The web UI is served from `./web` at `http://localhost:8080` by the dev script.
