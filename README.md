# linkedin-job-scraper
🔌 LinkedIn English EE Jobs Scraper — Italy
A Python scraper that finds entry-level Power & Electrical Engineering jobs in Italy, filtering only English-language postings by reading the actual job description.

🎯 What it does

Searches LinkedIn for junior/graduate engineering roles across 30+ keywords
Visits each job page and detects the language of the description
Keeps only English postings — skips Italian or other languages
Saves results to a clean english_ee_jobs_italy.json file
Targets major Italian employers: Enel, Eni, Snam, Terna, Leonardo, ABB, Siemens, STMicroelectronics, Baker Hughes, and more


🛠️ Tech Stack

requests — HTTP requests
BeautifulSoup — HTML parsing
langdetect — language detection
dataclasses + json — structured output


📦 Installation
bashpip install requests beautifulsoup4 langdetect

🚀 Usage
bashpython scraper.py
Results are printed to the terminal and saved to english_ee_jobs_italy.json.

⚙️ Configuration
In scraper.py, you can adjust:
ParameterDefaultDescriptionlocation"Italy"Job search locationmax_pages2Pages per keyword (25 results each)request_delay2.5sDelay between search pagesdesc_delay1.5sDelay between job page fetches

⚠️ Disclaimer
This tool uses LinkedIn's guest/public job search API. Use responsibly and respect rate limits. Not affiliated with LinkedIn.
