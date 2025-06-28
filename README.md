
# 🕵️‍♀️ HackerRank Plagiarism Checker

A web-based tool to detect plagiarism in code submissions of HackerRank contests using web scraping, natural language processing (NLP), and FastAPI.

---

## 🚀 Features

- ✅ Admin login to fetch contest data
- ✅ Web scraping of user submissions using Selenium
- ✅ SQLite database to store previous attempts
- ✅ NLP-based source code similarity check (using Sentence Transformers)
- ✅ Web interface to:
  - View submissions
  - Run plagiarism check
  - Display matched users and similarity scores

---

## 📂 Folder Structure

```

hackerrank-plagiarism-checker/
│
├── templates/                # HTML pages (UI)
│   ├── index.html
│   ├── userAttempts.html
│   └── result.html
│
├── hackerrank\_SQL.py         # Handles database operations
├── hackerrank\_main.py        # Main orchestrator for scraping and storing
├── hackerrank\_plagiarismCheck.py  # Plagiarism logic using embeddings
├── hackerrank\_selenium.py    # Web scraping using Selenium
├── main.py                   # FastAPI entry point
├── requirements.txt          # Python dependencies
├── readme.md                 # Project description
├── db.sqlite3                # (Optional) SQLite database

````

---

## ⚙️ Installation & Running Locally

### 1. Clone the Repo

```bash
git clone https://github.com/your-username/hackerrank-plagiarism-checker.git
cd hackerrank-plagiarism-checker
````

### 2. Install Dependencies

Make sure you have Python 3.8+ and `pip` installed.

```bash
pip install -r requirements.txt
```

### 3. Run the App

```bash
uvicorn main:app --reload
```

Then open [http://127.0.0.1:8000](http://127.0.0.1:8000) in your browser.

---

## 🧠 How It Works

1. **Admin logs in** and enters contest slug.
2. **Selenium scrapes** all users and their best attempts from HackerRank.
3. Data is stored in **SQLite** using `hackerrank_SQL.py`.
4. You can view all submissions via web UI.
5. When "Check Plagiarism" is clicked:

   * Code from other users is compared using **Sentence Transformers**.
   * Cosine similarity score is computed for each pair.
   * Results are displayed in a table.

---

## 💡 Technologies Used

* **Python**
* **FastAPI**
* **Selenium** (for web scraping)
* **Sentence Transformers** (MiniLM-L6-v2)
* **SQLite**
* **HTML + Jinja2 Templates**

---

## 📦 Requirements

```
fastapi
uvicorn
selenium
sentence-transformers
jinja2
sqlite3 (builtin)
```

Use `pip install -r requirements.txt` to install.

---

## 🔐 Admin Login Credentials

* Used only for accessing **HackerRank contest dashboard**
* Your email/password is **not stored**

## 🧑‍💻 Author

Bhanu Bhargavi
Built as part of a project to automate plagiarism detection in coding contests.

---

## 🛡️ Disclaimer

This tool is for **educational & ethical use** only. It is intended to identify possible duplicate submissions in internal contests for fair evaluation.

```


