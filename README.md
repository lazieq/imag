# IMAG – full-screen wrapper (GitHub Pages)

Static wrapper for the IMAG Apps Script web app: no Google "created by an Apps Script user" banner, fills the whole screen, IMAG icon on the home screen.

## Deploy (GitHub Pages)
1. Create a repo (e.g. `imag-app`), upload **all files in this folder** (including `.nojekyll`, `icons/`).
2. Settings → Pages → Source: *Deploy from a branch* → `main` / root → Save.
3. Open `https://<user>.github.io/imag-app/` → Add to Home Screen (iOS: Share → เพิ่มไปยังหน้าจอโฮม; Android/Chrome: ⋮ → ติดตั้งแอป).

## Change the app URL
Edit `APP_URL` in `index.html` (one line) and the `noscript` link if you redeploy to a new `/exec` URL.
(Editing an existing deployment → New version keeps the same URL — no change needed.)

## Notes
- The Apps Script deployment must stay **Who has access: Anyone** (no Google sign-in). With "Anyone with Google account"/domain, the iframe needs Google cookies, which Safari/iOS and Chrome block in third-party iframes.
- The query string is forwarded to the app (`?a=…&c=…`).
- Login (token in localStorage) is stored per top-level site, so users log in once in the wrapper separately from the direct link.
- No service worker on purpose (not needed for install; the app can't work offline anyway).
