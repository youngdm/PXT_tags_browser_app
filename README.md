# PXT Tags Browser App
This static HTML tool brings the Peatland eXchange Tags (PXT) workflow into any modern browser so you can standardize peatland metadata without a server or internet connection.

## What the App Does
- Replicates the original Python-based PXT Web App experience entirely in the browser: upload a CSV, preview the columns, assign PXT tags, validate required fields, and download an export that embeds those tags in the headers.
- Implements the full three-level tag hierarchy (site, event, dataset) defined in [PXT Tags v0.1.2](https://doi.org/10.5281/zenodo.17348933) while highlighting required, desirable, and optional priorities.
- Encourages privacy-first use (all processing is local, no data leaves your machine, and nothing is stored after you close the page) with tip bubbles that surface how to interact with the UI.

## How to Use the Browser App
1. Open `PXT_web_app_browser_301025.html` in your preferred browser (Chrome, Edge, Firefox, Safari, etc.). The page is self-contained: no build steps, no server, just double-click or drag into the browser window.
2. Upload your peatland dataset (CSV only). A sample file (`sample_peatland_study.csv`) is included for testing; you can also hit Ctrl+O / ⌘+O to trigger the file picker. The upload page explains the supported CSV format (header row, UTF-8/ASCII, quoted fields allowed).
3. After upload you land on the data preview screen where you can inspect field names, types, and a quick row sampling before moving on.
4. Map each column to a PXT tag via the dropdowns on the tagging screen. Suggested tags, badges, and tag priority markings make it easier to cover the required site/event/dataset metadata.
5. Click “Continue to Validation” to see which required tags are still missing, review a summary of assigned tags, and then download the tagged CSV. “Start New Upload” clears the current data so you can begin again with a different file.

## PXT Tag Reference
This browser app uses the same 55 tags defined in the documents at https://doi.org/10.5281/zenodo.17348933. The tags are grouped into:
- **Site level** (`#pxt_site_*`): physical location and site descriptors.
- **Event level** (`#pxt_event_*`): observations, measurements, and linked site IDs.
- **Dataset level** (`#pxt_dataset_*`): overall dataset metadata, title, description, keywords, and contact info.
For the complete definition of every tag and field, read the specification hosted at the DOI above (the markdown file lives in the legacy Python repo).

## Sample Data
Use `sample_peatland_study.csv` as a fabricated dataset for exploring the workflow. It mirrors the kinds of fields the tagging interface expects, so you can step through upload → preview → tagging → export without needing your own research data.

## Troubleshooting & Tips
- The page works offline, but it relies on browser memory—large datasets take longer to parse and render, so a dataset above ~50MB may feel sluggish but is still supported.
- Stick to CSV with a header row; empty columns or merged headers can confuse the parser.
- If validation reports missing required tags, revisit the tagging screen and assign the highlighted priorities before exporting.
- No data is transmitted anywhere: once you close or refresh the tab, all loaded content disappears.

## Support & Contribution
Raise issues or suggest improvements via this repo. Contributions (documentation fixes, sample data tweaks, interface polish) are welcome—just follow the coding conventions already in use. Licensed under the terms in `LICENSE`.
