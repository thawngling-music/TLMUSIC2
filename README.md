# TLMUSIC Full AI Studio — Integration Starter

This package adds a mobile-friendly AI Studio UI for:
- AI Chat
- Music Theory
- Chord Assistant
- Mixing Assistant
- Songwriting Assistant

It uses a small Node.js backend to call the Gemini API. The API key stays on the server, never in HTML/JavaScript shipped to the browser.

## Important status
This is an integration starter, not yet merged into your live GitHub repository. I could not directly retrieve or commit your repository source from this chat environment. Keep a backup of the current repository before integrating.

## Files
- `ai-studio.html` — standalone AI Studio page, designed to match TLMUSIC's dark green theme.
- `server.js` — protected API endpoint `/api/chat` plus health endpoint `/api/health`.
- `package.json` — Node dependencies.
- `.env.example` — example environment variable names; never put real secrets in this file.
- `INTEGRATION.md` — next steps.

## Run locally
Requires Node.js 20+ (Node 18+ may work if global `fetch` is available).

1. Copy these files into a new folder.
2. Run `npm install`.
3. Set `GEMINI_API_KEY` as an environment variable in your terminal or hosting dashboard.
4. Run `npm start`.
5. Open `http://localhost:3000/ai-studio.html`. The `public/` folder already contains the page and is served by the backend.
6. Test `GET /api/health`, then try each AI tool.

## Deployment notes
- A static-only host such as GitHub Pages cannot safely hold a private API key or run this Node backend. Keep the frontend on GitHub Pages if you want, but deploy `server.js` to a backend host and change the frontend fetch URL to your backend origin. Configure CORS allow-list on the backend before doing that.
- Add `GEMINI_API_KEY` using your backend host's environment/secrets settings.
- Check current Gemini API terms, model availability, quotas, and pricing before production use. Free-tier limits can change.
- Add CORS restrictions, authentication or an access token, stronger abuse protection, and monitoring before exposing a personal endpoint publicly.
- Do not commit `.env`, API keys, or credentials to GitHub.
