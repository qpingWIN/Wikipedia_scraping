# Wikipedia News Scraping (Jupyter Notebook)

A compact, reproducible project that scrapes **Wikipedia Current events** pages and structures the headlines into a tabular dataset (date, title, link, summary). It is designed as a clean, recruiter-friendly example of **web scraping, parsing (BeautifulSoup), and data wrangling (pandas)** in a Jupyter workflow.

---

## Contents

- `Wikipedia_scraping.ipynb` – the main notebook (your original file).
- `requirements.txt` – minimal dependencies to run the notebook.
- `.gitignore` – ignores caches, checkpoints, and large data.


---

## Setup

### `pip` 
```bash
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

Launch Jupyter:
```bash
jupyter lab   # or: jupyter notebook
```



## Usage (Notebook)

Open `Wikipedia_scraping.ipynb` and run cells top-to-bottom. The notebook shows how to:

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


Example: Export path

The notebook writes to wikipedia_in_the_news.csv:

- Libraries: **requests**, **BeautifulSoup (bs4)**, **pandas**.
