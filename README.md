# SQL Query Writer Agent — MindBridge AI Competition (Winter 2026)

My submission for the Carleton University / MindBridge AI Winter 2026 competition: an agent that translates natural language questions into SQL queries against a bike store database.

## What it does

`agent.py` implements a `QueryWriter` class that:
1. Takes a natural language question (e.g. "What are the top 5 best-selling products?")
2. Uses an open-source LLM (via Ollama, `llama3.2`) to understand the database schema and generate a query
3. Returns a valid SQL query that can be run against the bike store DuckDB database

## Tech stack

- **Ollama** running `llama3.2` for query generation
- **DuckDB** as the database engine
- Bike store dataset (brands, categories, customers, orders, order_items, products, staffs, stocks, stores)

## Running it

```bash
# create and activate a virtual environment
python -m venv myenv
source myenv/bin/activate  # or myenv\Scripts\activate on Windows

# install dependencies
pip install -r requirements.txt

# run
python main.py
```

You'll need Ollama installed locally (or access to a compatible server) with `llama3.2` pulled:

```bash
ollama pull llama3.2
```

## Project structure

```
├── agent.py          # QueryWriter class — core NL-to-SQL logic
├── main.py           # entry point for testing the agent
├── db/                # database loading / schema helpers
├── *.csv              # bike store sample data
└── requirements.txt
```

## Notes

This was my first project cloning and building on top of a shared team repo — originally scaffolded from Dr. Aras Kayvan's [competition template](https://github.com/araskay/carleton_competition_winter_2026) for MindBridge AI's Carleton competition. All agent implementation and query logic here is my own work.

## Credits

Competition organized by [MindBridge AI](https://mindbridge.ai) in partnership with Carleton University. Bike store dataset from the [Bike Store Sample Database](https://www.kaggle.com/datasets/dillonmyrick/bike-store-sample-database) on Kaggle.