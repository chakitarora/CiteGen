# CiteGen — PMID Citation Generator

**Paste a list of PubMed IDs. Get formatted citations in 9 styles. Export files your reference manager can open immediately.**

No account. No install. No data leaves your browser. One HTML file.

---

## What this is

CiteGen is a browser-based citation tool for researchers. You give it a list of PubMed IDs (PMIDs) and it fetches the full metadata for each paper directly from NCBI, then formats every citation simultaneously in 9 major styles. You can copy any individual citation, or download your entire reference list in formats that work natively with Mendeley, Zotero, EndNote, LaTeX, and Microsoft Word.

**Live tool:** `https://chakitarora.github.io/CiteGen`

---

## The gap this fills

Every researcher working on a manuscript eventually faces the same problem: you have a list of PMIDs — from a database search, a collaborator, or your own notes — and you need formatted references, fast, in multiple styles, and in a format your reference manager can actually import.

The existing options are all painful:

- **PubMed's own citation export** gives you one paper at a time, in limited formats, with no batch option
- **Google Scholar** requires searching each paper individually and clicking through menus
- **Zotero / Mendeley browser plugins** require the full software installed and often fail on institutional pages
- **NLM's Citation Exporter** is functional but dated, exports only to a handful of formats, and has no direct Mendeley XML option
- **Online citation generators** (CitationMachine, EasyBib) are cluttered with ads, require you to paste metadata manually, and export poorly

CiteGen solves all of this: paste a list of PMIDs, click once, and you have every citation format plus four export types ready in under a minute.

---

## How to use it

### Basic workflow

1. Find your PubMed IDs — from PubMed search results, a database export, or your notes
2. Paste them into the input box (one per line, or comma/space separated)
3. Set your preferred default display format (APA, Vancouver, etc.)
4. Click **Fetch & format citations**
5. Results appear in a sortable, searchable table
6. Click **▾ cite** on any row to expand the citation panel below it — switch between all 9 formats, copy, or view the abstract
7. Download the full set in your chosen export format

### Finding PMIDs

PMIDs are the 8-digit numbers in any PubMed URL or result — e.g. `https://pubmed.ncbi.nlm.nih.gov/37743532/` → PMID is `37743532`. You can also export them from:
- PubMed search results → **Save** → **Format: PubMed** → extract the `PMID` field
- Your existing Mendeley/Zotero library (right-click → copy citation info)
- Any paper's abstract page


### Working with the results table

After fetching, results appear as a table with columns for title, authors, journal, year, and PMID.

- **Search** — the search box filters across all fields (title, author, journal, year, PMID) in real time
- **Sort** — click any column header to sort; click again to reverse. An arrow indicator shows the active sort
- **Expand** — click **▾ cite** on any row to open an inline citation panel. Shows all 9 format tabs with a copy button for each. Multiple rows can be expanded at once
- **Format selector** — the dropdown next to the search box switches which citation style is shown in expanded rows
- **Pagination** — navigate pages with Prev/Next; adjust rows per page (10/25/50/100) from the selector on the right
- **Abstract** — inside any expanded row, click **▸ Abstract** to read the full abstract without leaving the page

### Upload option

If you have a `.txt` file with one PMID per line (e.g. a PubMed batch export), drop it into the upload zone instead of pasting.

---

## Citation formats

| Format | Used for |
|---|---|
| **APA 7th** | Psychology, social sciences, education, most US universities |
| **Vancouver** | Medicine, biomedicine, clinical journals (ICMJE standard) |
| **Nature** | Nature journals and most high-impact biology journals |
| **Harvard** | UK universities, general sciences |
| **MLA 9th** | Humanities, literature, language |
| **Chicago 17th** | History, arts, humanities |
| **IEEE** | Engineering, computer science, electronics |
| **NLM/MEDLINE** | National Library of Medicine standard, PubMed native |
| **AMA** | American Medical Association, medical journals |

---

## Export files and Mendeley / Zotero import

CiteGen generates four export types. Here is exactly how to use each one:

### .ris — RIS format (recommended for Mendeley)

RIS is the most universally supported import format for reference managers.

**Mendeley Reference Manager (desktop or web):**
1. Download `citations.ris` from CiteGen
2. Open Mendeley Reference Manager
3. Click **Add** → **Import Library**
4. Select `citations.ris`
5. Papers appear in your library immediately with full metadata

**Mendeley Desktop (legacy):**
1. Download `citations.ris`
2. Open Mendeley Desktop → **File** → **Import** → **RIS - Research Information Systems (*.ris)**
3. Select the file → all papers are added to your library

**Zotero:**
1. Download `citations.ris`
2. **File** → **Import** → select `citations.ris`

**EndNote:**
1. **File** → **Import** → **File** → select `citations.ris` → Import Option: **Reference Manager (RIS)**

### .xml — PubMed XML (best metadata completeness for Mendeley)

The XML export uses the PubMed article set format — the same format as a native PubMed export. Mendeley reads this natively.

**Mendeley:**
1. Download `citations_pubmed.xml`
2. **Add** → **Import Library** → select the `.xml` file

This format preserves the most metadata including MeSH terms, keywords, and full author names, making it the best choice if you want a complete Mendeley library entry.

### .bib — BibTeX (LaTeX and Mendeley/Zotero)

Use this if you are writing in LaTeX or want to import into Mendeley or Zotero as an alternative to RIS.

**LaTeX:**
Place `citations.bib` in your project folder, then reference it with:
```latex
\bibliographystyle{unsrt}  % or any style: apalike, ieeetr, etc.
\bibliography{citations}
```

**Mendeley:** **Add** → **Import Library** → select `citations.bib`

**Zotero:** **File** → **Import** → select `citations.bib`

### .txt — Formatted text

Plain text export of all citations in your currently selected format, numbered. Paste directly into Word, Google Docs, or any document. Also useful for supplementary material reference lists.

---

## Using Mendeley with Microsoft Word

Once your papers are in Mendeley, you can cite them directly in Word:

1. Install the **Mendeley Cite** add-in from the Microsoft AppSource (free)
2. In Word: **References** tab → **Mendeley Cite**
3. Search for papers by title or author, click to insert citation
4. Choose your output citation style in the Mendeley Cite panel
5. Generate a formatted reference list automatically

The `.ris` or `.xml` import from CiteGen gives you fully tagged entries so Mendeley Cite can format them correctly in any style.

---

## Getting an NCBI API key (optional)

Without a key, NCBI allows 3 requests/second. With a free key, this increases to 10 requests/second — roughly 3× faster for large batches.

1. Go to [ncbi.nlm.nih.gov/account](https://www.ncbi.nlm.nih.gov/account/)
2. Create a free NCBI account
3. Go to **Settings** → **API Key Management** → **Create an API Key**
4. Paste the key into the API key field in CiteGen

For lists under 30 papers, the difference is minor. For 100+ papers, an API key is recommended.

---

## Privacy

All processing happens in your browser. CiteGen makes two types of external requests only:

1. **NCBI E-utilities API** — to fetch paper metadata by PMID (the same API PubMed itself uses). No account or login required.
2. **Google Fonts** — to load the Lora, IBM Plex Mono, and Inter typefaces. Remove the `<link>` tag in the HTML if you need fully offline use.

No data is sent to any server operated by this tool. Your PMIDs and the fetched metadata stay in your browser session and are cleared when you close the tab.

---

## How it works

CiteGen uses the NCBI E-utilities `efetch` endpoint with `rettype=xml` to retrieve full PubMed article records. The XML is parsed in the browser using the native `DOMParser` API — no libraries. Citation formatting is implemented as pure JavaScript functions, one per style, each following the official style guide specifications. All four export formats (TXT, BibTeX, RIS, PubMed XML) are generated from the parsed metadata and downloaded as files using the `Blob` + `URL.createObjectURL` browser API.

| Component | Technology |
|---|---|
| Metadata retrieval | NCBI E-utilities REST API (`efetch`, `db=pubmed`, `rettype=xml`) |
| XML parsing | Native browser `DOMParser` |
| Citation formatting | Vanilla JavaScript |
| Export generation | `Blob` + `URL.createObjectURL` |
| Typography | Lora (serif) · IBM Plex Mono · Inter |
| Dependencies | None — single HTML file |

---

## Browser compatibility

Works in all modern browsers. No extensions or plugins required.

| Browser | Support |
|---|---|
| Chrome / Edge 90+ | ✅ Full |
| Firefox 90+ | ✅ Full |
| Safari 15+ | ✅ Full |
| Mobile Chrome / Safari | ✅ Full |

---

## Limitations

- **PMIDs only** — does not currently support DOIs, arXiv IDs, or ISBN. PMIDs cover all journals indexed in PubMed (biomedical literature).
- **Rate limiting** — without an API key, large lists (100+ papers) take a few minutes due to NCBI's 3 req/sec limit.
- **Preprints** — bioRxiv and medRxiv preprints that have not been assigned a PMID are not supported.

---

## License

MIT — free to use, modify, and share.
