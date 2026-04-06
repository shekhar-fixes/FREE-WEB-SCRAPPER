# 🕸️ Universal Web Scraper (Python + Playwright)

A powerful and extensible **web scraping framework** built using Python and Playwright. This tool is designed for extracting structured data from modern, dynamic websites (including JavaScript-heavy pages).

It is fully customizable and can be adapted for scraping **any type of data** such as businesses, products, listings, or search results.

---

## 🚀 Features

* 🌐 Scrapes dynamic websites (JavaScript-rendered content)
* ⚡ Built with Playwright for high reliability
* 📊 Outputs data in **CSV and JSON formats**
* 🧠 Clean, modular, and extensible architecture
* 🔄 Supports pagination / scrolling data extraction
* 🛠️ Easy to adapt for different scraping use-cases
* ▶️ Ready-to-run with minimal setup

---

## 📦 Requirements

* Python 3.8+
* Playwright
* Pandas (optional, depending on usage)

Install dependencies:

```bash
pip install playwright pandas
playwright install chromium
```

---

## 📁 Project Structure

```
project/
│
├── scraper.py        # Main scraping logic
├── output.csv        # Generated CSV file
├── output.json       # Generated JSON file
├── README.md         # Documentation
```

---

## ⚙️ Configuration

Modify these variables inside the script to adapt the scraper:

```python
SEARCH_QUERY = "your search query"
MAX_RESULTS  = 100
OUTPUT_CSV   = "output.csv"
OUTPUT_JSON  = "output.json"
HEADLESS     = True
```

You can change:

* Target website or search query
* Number of results to scrape
* Output file formats
* Browser visibility (headless or not)

---

## ▶️ Usage

Run the scraper:

```bash
python scraper.py
```

The script will:

1. Open the target website
2. Search or navigate to the desired data
3. Collect item URLs or entries
4. Extract structured data
5. Save results to CSV and JSON

---

## 🧠 How It Works

### 1. Data Collection Phase

* Searches or loads a listing page
* Scrolls dynamically to load more results
* Extracts individual item URLs

### 2. Data Extraction Phase

* Visits each item page
* Extracts structured fields using selectors
* Handles missing data safely

### 3. Data Storage

* Saves results in:

  * CSV (tabular format)
  * JSON (structured format)

---

## 🔧 Customization Guide

To adapt this scraper for any website:

### Modify Selectors

Update CSS selectors inside extraction functions:

```python
await page.query_selector("your-selector")
```

### Change Data Fields

Edit the data model:

```python
@dataclass
class Item:
    name: str
    price: str
    rating: str
```

### Add New Fields

Extend extraction logic:

```python
item.new_field = await safe_text(page, "selector")
```

---

## ⚠️ Best Practices

* Respect website **robots.txt**
* Avoid aggressive scraping (add delays)
* Use headers/user-agents if needed
* Handle rate limits and blocking
* Do not scrape private or restricted data

---

## 🤝 Contributing

Contributions are welcome!

1. Fork the repository
2. Create a feature branch
3. Commit changes
4. Submit a pull request

---

## 📜 License

This project is licensed under the **MIT License**.

---

## 💡 Future Improvements

* Proxy & IP rotation support
* CAPTCHA solving integration
* Multi-threaded / async parallel scraping
* GUI dashboard
* Database integration (MySQL / MongoDB)

---

## 📌 Notes

This project is intended as a **general-purpose scraping framework**.
You can easily adapt it for:

* E-commerce scraping
* Business listings
* Job portals
* Real estate data
* Social media (public data only)

---

⭐ If you find this useful, consider giving the repo a star!
