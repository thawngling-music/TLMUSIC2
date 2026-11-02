# Integration into the existing TLMUSIC repository

1. Make a backup / create a new branch before editing.
2. Add `ai-studio.html` to the root or a chosen public folder.
3. Add `server.js` and `package.json` to a separate backend deployment folder/repository. Do not assume GitHub Pages runs Node.js.
4. In the existing navigation, add an `AI Studio` link pointing to `ai-studio.html`. The existing `index.html`, `sw.js`, `manifest.webmanifest`, and current tools have not been modified by this starter.
5. Deploy the backend to a Node.js hosting service. Set `GEMINI_API_KEY` in the host's secret/environment settings.
6. If frontend and backend are on different origins, update `fetch('/api/chat', ...)` in `ai-studio.html` to the backend URL and add a strict CORS allow-list in `server.js`. Do not use wildcard CORS for a public API.
7. Test on iPhone Safari: AI Chat, Theory, Chords, Mixing, Songwriting, loading/error states, and small-screen layout.
8. Update the service worker cache version and cache list if you want offline shell caching. AI requests themselves require network access.
