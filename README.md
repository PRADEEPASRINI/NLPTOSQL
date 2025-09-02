# NLP-to-SQL: Talk to a Database

This is an end-to-end **LLM project** based on **LangChain and HuggingFace embeddings**. We are building a system that can talk to a **SQL database**.
Users ask questions in natural language, and the system generates answers by converting those questions into **SQL queries** and executing them on the database.
For example, a store manager may ask:

* How many white color Adidas t-shirts do we have left in stock?
* How much sales will our store generate if we sell all extra-small size t-shirts after applying discounts?

The system is intelligent enough to generate accurate queries for a given question and execute them on the SQL database.

![](atliq_tees.png)

## Project Highlights

* Works with a sample **T-shirt store database** (inventory, sales, and discounts).
* Built with:
  *Gemini API
  * HuggingFace embeddings
  * LangChain framework
  * SQLite / MySQL as the backend database
  * Streamlit for UI
  * Chromadb as a vector store
  * Few-shot learning for better SQL generation
* In the UI, a store manager can ask questions in natural language, and the system will produce accurate answers.

## Installation

1. Clone this repository to your local machine:

```bash
git clone https://github.com/your-username/NLPTOSQL.git
```

2. Navigate to the project directory:

```bash
cd NLPTOSQL
```

3. Install the required dependencies:

```bash
pip install -r requirements.txt
```

⚠️ **Troubleshooting:** If you face Keras-related errors such as:

```
ValueError: Your currently installed version of Keras is Keras 3, but this is not yet supported in Transformers.
```

Run the following fix:

```bash
pip uninstall -y keras keras-nightly keras-PreRelease
pip install tf-keras
```

4. For database setup, run the provided `.sql` script in your MySQL/SQLite environment.

## Usage

1. Run the Streamlit app:

```bash
streamlit run main.py
```

2. The web app will open in your browser, where you can ask questions.

## Sample Questions

* How many total t-shirts are left in stock?
* How many t-shirts do we have left for Nike in XS size and white color?
* How much is the total price of the inventory for all S-size t-shirts?
* How much sales amount will be generated if we sell all small size Adidas shirts today after discounts?

## Project Structure

* **main.py**: The main Streamlit application script.
* **langchain\_helper.py**: All LangChain code and embedding logic.
* **requirements.txt**: List of required Python packages.
* **few\_shots.py**: Contains few-shot prompts.
* **.env**: Configuration file (API keys if needed).
