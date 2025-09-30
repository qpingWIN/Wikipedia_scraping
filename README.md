# Wikipedia News Scraping (Jupyter Notebook)

A compact, reproducible project that scrapes **Wikipedia Current events** pages and structures the headlines into a tabular dataset (date, title, link, summary). It is designed as a clean, recruiter-friendly example of **web scraping, parsing (BeautifulSoup), and data wrangling (pandas)** in a Jupyter workflow.

> ⚠️ Always respect Wikipedia’s [Terms of Use](https://foundation.wikimedia.org/wiki/Policy:Terms_of_Use) and `robots.txt`. Scrape politely (rate-limit, identify your requests), cache locally when possible, and prefer the official APIs when they meet your needs.

---

## Contents

- `notebooks/Wikipedia_scraping.ipynb` – the main notebook (your original file).
- `requirements.txt` – minimal dependencies to run the notebook.
- `.gitignore` – ignores caches, checkpoints, and large data.
- `LICENSE` – MIT license (feel free to change).
- `data/` – (optional) folder for cached HTML and exported CSV.

Recommended repo layout:
```
wiki-news-scraper/
├─ notebooks/
│  └─ Wikipedia_scraping.ipynb
├─ data/
│  ├─ raw/           # cached HTML (optional)
│  └─ processed/     # CSV/Parquet exports
├─ README.md
├─ requirements.txt
├─ LICENSE
└─ .gitignore
```

---

## Setup

### Option A: `pip` (quick)
```bash
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

### Option B: `conda`
```bash
conda create -n wiki-scrape python=3.11 -y
conda activate wiki-scrape
pip install -r requirements.txt
```

Launch Jupyter:
```bash
jupyter lab   # or: jupyter notebook
```

---

## Usage (Notebook)

Open `notebooks/Wikipedia_scraping.ipynb` and run cells top-to-bottom. The notebook shows how to:

1. **Fetch** a Wikipedia Current events page (requests with polite headers + delay).
2. **Parse** the HTML with **BeautifulSoup** (bs4) to extract date sections and items.
3. **Structure** the data into a **pandas DataFrame** with columns such as:
   - `date` (datetime)
   - `headline` / `title`
   - `link` (absolute URL)
   - `summary` (if available)
   - `category` (if parsed)
4. **Export** results to `data/processed/wikipedia_current_events.csv`.

> Tip: Keep a small **date range** (e.g., a month) for demos; long date ranges increase requests and runtime.

---

## Configuration & Etiquette

- **Rate limiting:** add a small `time.sleep(1)` between requests.
- **Identify your client:** set a descriptive `User-Agent` in `requests.get(..., headers=...)`.
- **Caching:** optional – store raw HTML under `data/raw/` to avoid re-downloading.
- **API alternative:** for many use cases, Wikipedia’s REST / MediaWiki API is preferable to scraping HTML.

---

## Reproducibility

To ensure deterministic runs:
- Pin package versions in `requirements.txt`.
- Save a timestamped CSV export to `data/processed/`.
- Clear notebook outputs before committing (keeps diffs small).

---

## Example: Export path

The notebook writes to (create folders if missing):
```
data/processed/wikipedia_current_events.csv
```

---

## License

This project is licensed under the **MIT License** – see `LICENSE` for details.

---

## Credits

- Wikipedia contributors for the underlying content.
- Libraries: **requests**, **BeautifulSoup (bs4)**, **pandas**.
