# 📝 NLP-to-SQL Converter

This project allows users to **ask natural language questions** (e.g., "How many blue T-shirts are in stock?") and get back the corresponding **SQL query** and **results** from a database. Built using **LangChain**, **HuggingFace embeddings**, and a sample SQLite database.

---

## 🚀 Features

* Convert **plain English** to **SQL queries**.
* Run queries against a **T-shirts inventory database**.
* Uses **LangChain + HuggingFace embeddings** for semantic understanding.
* Easy to extend with new datasets.

---

## 🛠️ Installation

1. **Clone this repository**

```bash
git clone https://github.com/your-username/NLPTOSQL.git
cd NLPTOSQL
```

2. **Create a virtual environment**

```bash
python -m venv venv
source venv/bin/activate   # On Linux/Mac
venv\Scripts\activate      # On Windows
```

3. **Install dependencies**

```bash
pip install -r requirements.txt
```

⚠️ If you face Keras errors, run:

```bash
pip uninstall -y keras keras-nightly keras-PreRelease
pip install tf-keras
```

---

## 📂 Project Structure

```
NLPTOSQL/
│── main.py                 # Entry point
│── langchain_helper.py      # LangChain logic & embeddings
│── tshirt.db                # SQLite database (sample data)
│── requirements.txt         # Dependencies
│── README.md                # Project documentation
```

---

## ▶️ Usage

Run the main file:

```bash
python main.py
```

Example interaction:

```
User: Show me all blue cotton T-shirts in XL size
SQL: SELECT * FROM tshirts WHERE color='Blue' AND cloth_type='Cotton' AND size='XL';
Result: [ ("Women T-shirt", "Cotton", "Blue", "XL", 100), ... ]
```

---

## ⚙️ Tech Stack

* **Python 3.10+**
* **LangChain**
* **Sentence-Transformers (HuggingFace)**
* **SQLite3**

---

## 📊 Database Schema

Sample `tshirts` table:

```sql
CREATE TABLE tshirts (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    item TEXT,
    cloth_type TEXT,
    color TEXT,
    size TEXT,
    quantity INTEGER
);
```

---

## 🧪 Example Queries

| Natural Language Question            | SQL Query                                                                                |
| ------------------------------------ | ---------------------------------------------------------------------------------------- |
| "List all black polyester T-shirts." | `SELECT * FROM tshirts WHERE color='Black' AND cloth_type='Polyester';`                  |
| "How many blue pants in L size?"     | `SELECT SUM(quantity) FROM tshirts WHERE item='Men Pant' AND color='Blue' AND size='L';` |

---

## 🤝 Contribution

1. Fork the repo
2. Create a feature branch (`feature-new`)
3. Commit changes (`git commit -m 'Added new feature'`)
4. Push branch (`git push origin feature-new`)
5. Create a Pull Request

---

## 📜 License

This project is licensed under the **MIT License**.

---

## 👤 Author

**Pradeepa S** ✨

---

🔥 Now you can query databases in plain English!
