# Happy Diwali — Web build output

This folder contains the web build artifacts for the "Happy Diwali" interactive bundle. It's ready to be served from any static web host (Netlify, Vercel, GitHub Pages, S3, etc.) or previewed locally.

Files and purpose

- `happy_diwali.wasm.html` — The demo HTML page. Open this in a browser (served over HTTP) to view the Diwali experience.
- `happy_diwali.wasm.js` — The JavaScript loader/entry used by the page to bootstrap the WebAssembly module and other assets.
- `happy_diwali.wasm.wasm` — The compiled WebAssembly binary containing the main application logic.
- `happy_diwali.wasm.pck` — An asset/package file used by the app to load media or data at runtime.
- `happy_diwali.wasm.png` / `happy_diwali.wasm.icon.png` / `happy_diwali.wasm.apple-touch-icon.png` — Image assets used by the page (icons, thumbnails).
- `*.import` files — Small marker files used by some deployment systems; they can usually be ignored.
- `happy_diwali.wasm.audio.worklet.js` & `happy_diwali.wasm.audio.position.worklet.js` — Web Audio Worklet scripts for spatial audio and sound processing.

Quick preview (local)

1. Run a simple HTTP server from this folder. Using PowerShell you can run:

```powershell
# From the output folder:
# Python 3 built-in server (recommended if Python is installed)
python -m http.server 8000

# Or, using Node.js http-server if installed:
npx http-server -p 8000
```

1. Open the demo in a modern browser (Chrome, Edge, or Firefox): [http://localhost:8000/happy_diwali.wasm.html](http://localhost:8000/happy_diwali.wasm.html).

Notes and tips

- Serve over HTTP(S): Most browsers restrict WebAssembly and Worklets when opening `file://` directly. Use a local server.
- Content-type: Ensure your static host serves `.wasm` with `application/wasm` and JS files with `text/javascript`.
- Caching: For iterative development, disable aggressive CDN caching for `.wasm`/`.js` to avoid stale assets.

Deployment

- Vercel / Netlify / GitHub Pages: Drop this folder as a static site or point your publish directory to it.
- S3 + CloudFront: Upload files and set proper MIME types; enable distribution to serve globally.

Credits

- Built for a Diwali celebration bundle. Enjoy and share responsibly.

If you want, I can:

- add a small `preview` script (Node) to start the server automatically,
- add a tiny `package.json` with dev commands,
- or create a one-click Vercel deployment config.
