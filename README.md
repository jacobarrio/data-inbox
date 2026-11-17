# Data Inbox

**Live demo: https://jacobarrio.github.io/data-inbox/**

An interactive prototype of automated data entry for small and mid-sized manufacturers. It turns the messy documents a business gets every week (customer POs, supplier invoices, inventory counts, spreadsheet exports) into clean, consistent data and a live dashboard, with no retyping.

## What it does

- **Reads mixed documents:** email text, PDFs, Excel workbooks (every sheet), CSV and pasted text.
- **Extracts line items:** part numbers, descriptions, quantities, prices, PO and invoice numbers, dates, customers and suppliers.
- **Cleans any spreadsheet automatically:**
  - trims stray spaces and standardizes mixed date formats
  - converts text numbers like `$1,200` or `42 lbs` into real numbers
  - normalizes part codes (`cpf 1042` → `CPF-1042`) and phone numbers
  - unifies spelling variants of the same company (`acme corp` / `ACME Corp.`)
  - removes blank and duplicate rows
- **Cross-checks the data:**
  - invoice math (qty × price vs billed)
  - invoice price vs the agreed PO price
  - duplicate invoices (prevents double payment)
  - customer demand vs stock on hand, and reorder points
  - inconsistent pricing across customers
- **Shows the results:** a before/after view of every cleaned file, a dashboard of flagged issues, a demand-vs-stock chart, and a savings calculator.

Everything runs in the browser. Uploaded files are processed locally and never sent anywhere or stored.

## Try it

1. Open the live demo and click **Run automation**.
2. Edit any sample document (change a price or quantity) and re-run to watch the checks react.
3. Click **New random week** for a fresh set of documents and errors.
4. Drop in your own messy Excel, CSV or PDF file.

## Stack

Plain HTML/CSS/JavaScript in a single file, with no build step. [SheetJS](https://sheetjs.com/) reads Excel files and [PDF.js](https://mozilla.github.io/pdf.js/) reads PDFs. Extraction and cleaning use a rules engine; a production build adds AI extraction for any document layout, OCR for scanned PDFs, and direct integration with the client's ERP, accounting software or Google Sheets.

All companies, parts and figures in the demo are fictional sample data.

## Contact

**Jacob Lee**, AI & Data Automation, Vancouver, WA
(564) 888-3442 · jacob61185@gmail.com
