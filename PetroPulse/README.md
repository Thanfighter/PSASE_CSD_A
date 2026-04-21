# PetroPulse

**PetroPulse** is a real-time news analytics dashboard that empowers oil and gas professionals with targeted insights from trusted energy news sources. Built using Streamlit, NLP, and topic modeling, the app filters and analyzes industry news articles with sentiment scoring and topic classification.

---

## 🚀 Live App

**[Launch PetroPulse](https://petropulse.streamlit.app)**

---

## 🛠 Features

* **Real-time News Ingestion:**

  * Scrapes news from trusted sources (e.g., BBC, Energy Voice, Kosmos Energy, etc.)
  * Ingests article title, source, published date, link, and full content

* **Keyword & Topic Filtering:**

  * Filters articles using a comprehensive list of energy-related keywords
  * Adds topic tags (e.g., Hydrogen, Oil & Gas, CCS, AI, Energy Policy)

* **Sentiment Analysis:**

  * Classifies news as Positive, Neutral, or Negative
  * Computes average sentiment index over a selected date range

* **Interactive Dashboard:**

  * Filter by date range, source, or topic
  * View articles in a table with sentiment and direct read link

---

## 📊 Technologies Used

* **Frontend:** [Streamlit](https://streamlit.io)
* **Data Processing:** `pandas`, `datetime`, `Altair`
* **NLP & Classification:** Custom keyword/topic filter, sentiment scoring module
* **Database:** SQLite (via SQLAlchemy)
* **Web Scraping:** Custom RSS feed parsing

---

## 🧠 Smart Tagging Logic

The pipeline tags each article based on its content using a curated keyword dictionary:

```python
{
  "Hydrogen": ["hydrogen", "H2", "electrolyzer"],
  "CCS": ["carbon capture", "sequestration"],
  "AI": ["machine learning", "AI", "NLP"],
  "Oil & Gas": ["upstream", "EOR", "drilling"],
  "Energy Policy": ["regulation", "DOE", "IEA"]
}
```

---

## 📁 Folder Structure

```bash
├── app/
│   └── PetroPulse.py              # Streamlit dashboard UI
├── src/
│   ├── models/
│   │   └── sentiment.py          # Sentiment scoring function
│   ├── nlp/
│   │   └── entities.py           # Topic classification logic
│   ├── scrapers/
│   │   └── news_scraper.py       # RSS feed scraper
│   └── storage/
│       └── db.py                 # SQLite DB functions
├── data/processed/insights.sqlite # Article storage
├── ingest.py                    # CLI ingestion tool
├── migrate_add_content.py      # One-time DB migration script
```

---

## ⚙️ How to Run Locally

### 1. Clone the Repo

```bash
git clone https://github.com/zainab-iyiola/PetroPulse.git
cd PetroPulse
```

### 2. Install Dependencies

```bash
python -m venv .venv
source .venv/bin/activate  # or .venv\Scripts\activate on Windows
pip install -r requirements.txt
```

### 3. Run the App

```bash
streamlit run app/PetroPulse.py
```

### 4. Ingest News (Optional)

```bash
python ingest.py --days 7 --per-feed 25
```


