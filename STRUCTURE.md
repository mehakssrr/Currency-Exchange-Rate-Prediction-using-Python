# Project Structure

```
forex-rate-prediction/
├── README.md              # Project overview, setup, and usage instructions
├── requirements.txt        # Python dependencies
├── .gitignore               # Files/folders excluded from git (datasets, caches, etc.)
├── src/
│   └── main.py             # Main script: load data, visualize, train Decision Tree model
├── data/
│   └── forex_data_2020-2025.csv   # (not tracked in git — add your own CSV here)
└── outputs/
    └── (generated plots / prediction CSVs go here, if you choose to save them)
```

## Folder notes

- **`src/`** — All source code lives here. `main.py` currently expects the dataset at `../data/forex_data_2020-2025.csv` (relative to `src/`).
- **`data/`** — Place your `forex_data_2020-2025.csv` file here. Raw data is excluded from git via `.gitignore` since datasets can be large and/or shouldn't be versioned — only a `.gitkeep` placeholder is tracked so the folder exists after cloning.
- **`outputs/`** — Optional destination for saved plots, prediction CSVs, or trained models. Also excluded from git by default; update `.gitignore` if you'd like to track specific output files.

## Getting started

```bash
git clone <your-repo-url>
cd forex-rate-prediction
pip install -r requirements.txt
# Add forex_data_2020-2025.csv to the data/ folder
python src/main.py
```
