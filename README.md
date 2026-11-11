<p align="center"><img src="logo.png" alt="Transport Bill Converter logo" width="160"></p>

# Transport Bill Converter

A browser-only tool that converts your **Transport Bill** Excel file into the **Loading and Unloading report** (30 columns, same layout as before), with checks, summaries and a neatly formatted Excel file.

Nothing is uploaded: the Excel file is read and written inside your browser. It works **offline** and needs no libraries for `.xlsx` and `.csv` files.

## What is new compared with the old converter

- Works offline (no internet or CDN needed for `.xlsx` / `.csv`)
- Finds the header row automatically (title rows above it are fine)
- Add **several files** at once, merged into one report; choose the sheet per file (`Sheet2` is preferred, else the first sheet)
- Dates and times appear **exactly as formatted in the source** (or choose dd-mmm-yyyy, dd/mm/yyyy, yyyy-mm-dd)
- Carton Qty and Vehicle Rent saved as real numbers, so Excel can add them (can be turned off)
- **Audit checks**: missing columns, missing vehicle / challan / date / rent, rent that is not a number, zero rent, possible duplicates, skipped Total rows, rows without unloading date, and a row-count / totals reconciliation
- Live preview, KPI tiles and breakdowns by vehicle company, buyer, vehicle number and date
- Styled Excel: frozen headers, filter, print titles, column widths, plus **Summary** and **Audit** sheets
- CSV download
- Column mapping: pick a different source column if your file uses other headings
- Settings (company name, title, parking place, C & F name, ...) saved in your browser

The default title still reads "Loading and Unloding Report" as in the original; change it in **Settings** if you want the spelling corrected.

## How to use

1. Open the page (see below).
2. Click the box or drop your `.xlsx` / `.csv` file(s) anywhere on the page.
3. Check the audit and preview, then press **Download Excel (.xlsx)**.

Try it with `sample/sample_transport_bill.xlsx` (fake data).

Older `.xls` files need the SheetJS library, loaded from a CDN only when such a file is added. If you are offline, save the file as `.xlsx` first.

## Run it

Open `index.html` in Chrome, Edge, Firefox or Safari. Or serve the folder:

```bash
python3 -m http.server 8000
```

**GitHub Pages:** push the repo, then *Settings → Pages* → source **GitHub Actions** (the included workflow publishes on every push to `main` or `master`), or **Deploy from a branch** → `main` → `/ (root)`. Your site address is `https://YOUR-USERNAME.github.io/REPO-NAME/`.

## Project structure

```
index.html              the whole app in one self-contained file
logo.png, icons/        logo, favicons, apple-touch and maskable icons
manifest.webmanifest    installable-app manifest
sample/                 sample input file with fake data
.github/workflows/      optional GitHub Pages deployment
```

## License

MIT, see [LICENSE](LICENSE).
