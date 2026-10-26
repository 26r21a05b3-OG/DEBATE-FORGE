# DebateForge Frontend

A futuristic responsive single-page DebateForge frontend. Open `index.html` in a browser to preview the fully interactive **demo mode**. No build tools required.

## Real AI integration

In Settings, enter the URL of your own deployed backend. Do **not** put API keys in the frontend.

The current frontend expects:
- `POST /api/debates` with JSON `{ "question": "...", "rounds": 3, "category": "..." }` returning `{ "id": "..." }` or `{ "debate_id": "..." }`.
- `GET /api/debates/{id}` returning `{ "status": "running|completed|failed", "current_round": 1, "messages": [{"agent":"Proposer","round":1,"content":"..."}], "verdict": "..." }`.
- CORS configured to permit the frontend's origin.

The frontend polls the backend every 1.5 seconds and has a two-minute client timeout. The API contract may need adaptation for your backend. The stop button aborts the frontend request, not necessarily the server-side job. Demo mode is illustrative and does not call AI or retrieve sources. History is stored in browser localStorage.

## Deploy

Upload `index.html` to any static web host (Netlify, GitHub Pages, Vercel, etc.). Use HTTPS for production.

## Publish with GitHub Pages (no build step)

1. Create a **public** repository on GitHub, for example `debateforge`.
2. Upload the **contents of this ZIP** to the repository root (not the ZIP itself): `index.html`, `README.md`, and `.nojekyll`.
3. Commit the files to the `main` branch.
4. Open **Settings → Pages** and choose **Deploy from a branch**, branch **main**, folder **/(root)**, then **Save**.
5. After deployment, visit `https://YOUR-USERNAME.github.io/debateforge/` (replace the username and repository name).

This is a static frontend. It works in clearly labeled demo mode without an AI API. For real AI debates, deploy a compatible backend separately, configure its URL in Settings, and enable CORS for the GitHub Pages origin. Never commit private API keys.


## Neon Command Center upgrade

Version 2 adds animated energy particles, neon agent orbits, holographic panels, responsive lighting and reduced-motion support. Existing debate functionality and demo/backend settings remain intact.

## Publish on GitHub Pages

Upload **the contents of this folder** to the root of your public repository (not the ZIP itself), then open Settings > Pages > Deploy from a branch > main / root. Never commit a Gemini API key. GitHub Pages hosts the static frontend only; real AI calls need a separately deployed backend.
