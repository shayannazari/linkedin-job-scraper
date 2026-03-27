# LinkedIn Job Scraper

A Python script that scrapes LinkedIn job postings without needing any API key or login.
It filters results by language, experience level, date posted, and location — all through a simple interactive prompt.

Built with **Electrical Engineering** job titles by default, but easily customizable for any field.

---

## Features

- No LinkedIn account or API key required
- Searches across multiple job title keywords automatically
- Filters job postings by language (detects the actual language of each job description)
- Interactive setup — no config files to edit before running
- Saves results to a JSON file
- Skips duplicate listings across keywords
- Handles missing pages gracefully — won't crash if you request more pages than LinkedIn has

---

## Requirements

Python 3.7 or higher, plus these libraries:

```bash
pip install requests beautifulsoup4 langdetect
```

If you are running this in **Google Colab**, add a `!` at the start:

```bash
!pip install requests beautifulsoup4 langdetect
```

---

## How to Use

**1. Download or clone the script**

```bash
git clone https://github.com/your-username/linkedin-job-scraper.git
cd linkedin-job-scraper
```

**2. Run the script**

```bash
python linkedin_job_scraper.py
```

**3. Answer the prompts**

The script will walk you through 5 steps:

```
STEP 1 - Select your experience level
  1. Internship
  2. Entry level
  3. Associate
  4. Mid-Senior level
  5. Director
  6. Executive

STEP 2 - Select preferred job posting language
  1. English   2. Dutch   3. German   4. French   5. Spanish
  6. Italian   7. Portuguese   8. Polish   9. Swedish   10. Danish
  11. Norwegian   12. Finnish   13. Arabic   14. Turkish   15. Romanian

STEP 3 - Select date posted
  1. Any time
  2. Past month
  3. Past week
  4. Past 24 hours

STEP 4 - Enter location
  Country (e.g. Germany, Italy, Netherlands)
  City     (optional — leave blank to search the whole country)

STEP 5 - How many pages per keyword?
  Each page contains up to 25 job listings.
  Recommended: 1-2 pages for speed, 3-5 for more results.
  If LinkedIn has fewer pages than you requested, the script stops automatically.
```

**4. Wait for results**

The script will check each listing, detect the language of the job description, and save only the ones matching your chosen language. When finished, results are printed to the console and saved to a JSON file in the same folder.

---

## Output

Results are saved to a file named like:

```
linkedin_jobs_Italy_it.json
```

Each job entry contains:

| Field | Description |
|---|---|
| `title` | Job title |
| `company` | Company name |
| `location` | Job location |
| `posted` | When it was posted |
| `job_url` | Direct link to the listing |
| `language` | Detected language of the description |
| `description_snippet` | First 300 characters of the job description |

---

## Customizing for Your Field

The script comes pre-loaded with **28 Electrical Engineering job titles** (power systems, embedded, hardware, firmware, automation, and more).

If your field is different, open the script and find the `CONFIGURATION` section near the top. Replace the `JOB_KEYWORDS` list with titles relevant to your field.

**Example — Software Engineering:**

```python
JOB_KEYWORDS = [
    "Software Engineer",
    "Backend Developer",
    "Frontend Developer",
    "Full Stack Developer",
    "Python Developer",
    "DevOps Engineer",
    "Cloud Engineer",
    "Site Reliability Engineer",
]
```

**Example — Mechanical Engineering:**

```python
JOB_KEYWORDS = [
    "Mechanical Engineer",
    "Design Engineer",
    "Manufacturing Engineer",
    "Structural Engineer",
    "CAD Engineer",
    "HVAC Engineer",
    "Automotive Engineer",
]
```

**Example — Data & AI:**

```python
JOB_KEYWORDS = [
    "Data Engineer",
    "Data Scientist",
    "Machine Learning Engineer",
    "AI Engineer",
    "Data Analyst",
    "MLOps Engineer",
    "NLP Engineer",
]
```

That is the only change needed. Everything else (prompts, scraping, language detection, output) works the same for any field.

---

## Tips

- **Too few results?** Choose "Any time" for the date filter, or search the whole country instead of a specific city.
- **Wrong language results?** The language filter works on the actual text of the job description — some postings mix languages, which can cause occasional mismatches.
- **Rate limiting?** If LinkedIn blocks requests, try reducing the number of pages per keyword or running the script again after a few minutes.
- **Google Colab users:** The interactive prompts work fine in Colab notebooks.

---

## Disclaimer

This tool is for personal job searching only. It accesses LinkedIn's public guest job search pages (no login required). Use responsibly and in line with LinkedIn's Terms of Service.

---

## License

MIT — free to use, modify, and share.
