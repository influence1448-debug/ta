# Tarangan Associates — static deployment package

This is a plain static website, not a Vite/React project. Keep all files in this folder at the **repository root**. Do not place them inside `src/`, `dist/`, or an extra nested folder.

## Files
- `index.html` — website shell
- `app.js` — page renderer, hash navigation, interactions
- `styles.css` — styles
- `public/Real-Estate-video-SnapYT.App.mp4` — hero video
- `vercel.json` — Vercel filesystem/fallback routing
- `netlify.toml` and `_redirects` — Netlify publish/fallback configuration

## Vercel setup
1. Push the **contents of this folder** to the root of your GitHub repository. The root should visibly contain `index.html`, `app.js`, `styles.css`, `public/`, and `vercel.json`.
2. In Vercel → Project → Settings → Build and Deployment, choose **Other** as Framework Preset.
3. Clear Build Command and Install Command. Set Output Directory to `.` if the dashboard requires it. Do not set it to `dist` or `src`.
4. Redeploy the latest commit from Deployments. Open the deployment URL, not a preview/editor/agent-run URL.

## Netlify setup
1. Either import the same GitHub repository, or drag-and-drop the **contents of this folder** (not the ZIP itself and not the parent folder) into Netlify's manual deploy drop zone.
2. For a Git-connected deploy, publish directory is `.` and no build command is needed. `netlify.toml` sets this automatically.
3. Open the public site URL shown under **Deploys**, not an Agent Run preview URL.

## Test after deploy
- Homepage should load at `/`.
- The site changes pages using `/#/about`, `/#/projects`, etc.
- The video should load from `/public/Real-Estate-video-SnapYT.App.mp4`.
- If an old 404 persists, verify the latest deployment's root file listing includes `index.html`; an old project output setting or deploying the parent folder is the usual cause.
