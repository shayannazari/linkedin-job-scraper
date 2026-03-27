# 🔌 LinkedIn English EE Jobs Scraper — Italy

A Python scraper that finds **entry-level Power & Electrical Engineering jobs in Italy** on LinkedIn, filtering only **English-language postings** by reading the actual job description.

---

## 🎯 What It Does

- Searches LinkedIn for junior/graduate engineering roles across **30+ keywords**
- Visits each job page and **detects the language** of the description
- Keeps only **English postings** — skips Italian or other languages
- Saves results to a clean `english_ee_jobs_italy.json` file
- Targets major Italian employers: **Enel, Eni, Snam, Terna, Leonardo, ABB, Siemens, STMicroelectronics, Baker Hughes**, and more

---

## 🛠️ Tech Stack

- [`requests`](https://pypi.org/project/requests/) — HTTP requests
- [`BeautifulSoup`](https://pypi.org/project/beautifulsoup4/) — HTML parsing
- [`langdetect`](https://pypi.org/project/langdetect/) — Language detection

---

## 📦 Installation

```bash
pip install requests beautifulsoup4 langdetect
```

---

## 🚀 Usage

```bash
python scraper.py
```

Results are printed to the terminal and saved to `english_ee_jobs_italy.json`.

---

## ⚙️ Configuration

You can adjust these parameters inside `scraper.py`:

| Parameter | Default | Description |
|---|---|---|
| `location` | `"Italy"` | Job search location |
| `max_pages` | `2` | Pages per keyword (25 results each) |
| `request_delay` | `2.5s` | Delay between search pages |
| `desc_delay` | `1.5s` | Delay between individual job fetches |

---

## 📁 Output Example

```json
[
  {
    "title": "Junior Electrical Engineer",
    "company": "Enel",
    "location": "Rome, Italy",
    "posted": "2 days ago",
    "job_url": "https://www.linkedin.com/jobs/view/...",
    "job_id": "1234567890",
    "language": "en",
    "description_snippet": "We are looking for a motivated junior electrical engineer..."
  }
]
```

---

## ⚠️ Disclaimer

This tool uses LinkedIn's public guest job search. Use responsibly and respect rate limits. Not affiliated with LinkedIn.

---

## 📄 License

MIT License — feel free to use, modify, and share.
