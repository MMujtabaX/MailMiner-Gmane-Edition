# 📧 Gmane Email Archive Analysis

This repository contains a set of Python scripts that collectively form a complete pipeline to **extract**, **process**, and **analyze** public email data from the [Gmane](http://www.gmane.org/) archive, particularly focusing on the `sakai.devel` mailing list. 

<p align="center"> <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExNm92d2tjN3NwcDNibXZheTBoY2NlOWZ0Mm9yazdjdHEwNTY3dXJsbCZlcD12MV9naWZzX3NlYXJjaCZjdD1n/vzTDTS5mev6vAf3Eiz/giphy.gif" alt="Gmane Project Demo" width="700"/> </p>

---

## 🧠 Project Overview

The main goal of this project is to practice web scraping, data processing, and visualization using email data from a real-world source. It demonstrates working with:
- Web scraping and HTML parsing
- SQLite database creation and management
- Email parsing and normalization
- Data compression using `zlib`
- Text processing (cleaning, frequency analysis)
- Simple data visualizations using JavaScript

---

## 🗂️ Components

| File | Description |
|------|-------------|
| `spider.py` | Downloads email messages from Gmane archive and stores them into `content.sqlite`. |
| `gmodel.py` | Extracts and normalizes email metadata (sender, subject, date) into `index.sqlite` using domain mapping. |
| `gbasic.py` | Generates statistics about top contributors and top email domains. |
| `gword.py` | Analyzes and extracts the most common words in email subjects and generates a word cloud (`gword.js`). |
| `gline.py` | Analyzes email traffic by year and domain and generates a line chart dataset (`gline.js`). |

---

## 📊 Outputs

Once the pipeline is run, you’ll get:

- **`index.sqlite`** – Processed and normalized email metadata.
- **`gword.js`** – Data for subject word cloud.
- **`gline.js`** – Data for visualizing messages per domain per year.
- **HTML visualizations** (open in browser):
  - `gword.htm`
  - `gline.htm`

---

## 🔧 Requirements

- Python 3.x
- `sqlite3`
- `zlib`
- `dateutil`
- `BeautifulSoup` (if using additional visualization)
- Internet connection for `spider.py`

Install missing packages using pip:

```bash
pip install python-dateutil
