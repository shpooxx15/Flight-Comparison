# Flight Comparison

Browser-only Trip.com flight comparison and XLSX export. It accepts Trip.com PDFs with a readable text layer and locally saved Trip.com HTML pages. No backend, account, database, or flight data persistence. PDF.js and SheetJS are loaded from their public CDNs; an internet connection is required to load the app libraries.

## Run locally

Open `index.html` in a modern browser over HTTP (for example, use any static file server). PDF.js module loading may be blocked by `file://` browser restrictions. The app itself has no build step.

## Deploy to GitHub Pages

1. Push this repository to GitHub.
2. In repository **Settings → Pages**, choose **Deploy from a branch**.
3. Select the default branch and `/ (root)`, then save.
4. Open the published URL. The project uses relative asset paths and works from a GitHub Pages project subpath; PDF.js worker and libraries load from public CDNs.

## Notes

All flight records remain in in-memory page state and disappear on reload. Only column visibility and page size are stored as browser preferences. Trip.com PDFs vary by locale and layout; the parser groups positioned text by page lines and attempts to isolate flight-card blocks. For image-only PDFs, use Chrome's **Save Page As → Webpage, Complete**, then upload the resulting `.html` file. The HTML parser targets Trip.com's `u-flight-card` card structure and ignores filters, advertising, and hotel bundles. No OCR or remote parsing is used.
