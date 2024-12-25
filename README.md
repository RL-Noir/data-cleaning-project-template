![Cover Image](future_office.jpg)

# Data Cleaning Project Template

This repository does not include a license. Users are encouraged to add their own based on their project requirements.

## Overview

This template is designed to streamline data cleaning projects. It simplifies the project structure for beginners and focuses on organizing datasets and cleaning scripts.

> **Note**: This template does not include preinstalled dependencies. You can customize the `requirements.txt` file for your project's needs.

## Project Organization

```
data_cleaning_project/
├── LICENSE            <- (Optional) Assign the appropriate license
├── README.md          <- Project overview and instructions
├── .gitignore         <- Defines files and folders to be ignored by Git
├── data               <- Datasets folder
│   ├── cleaned        <- Cleaned datasets ready for analysis
│   ├── garbage        <- Data identified as unusable during cleaning
│   ├── raw            <- Original data files
│   ├── raw_chunks     <- Optional: Chunked raw data
├── logs               <- Logs for tracking processes and errors
├── notebooks          <- Jupyter notebooks for data cleaning and exploration
├── requirements.txt   <- Dependencies for the project
├── src                <- Source code folder
│   ├── __init__.py    <- Marks src as a Python module
│   ├── data_cleaning.py <- Main scripts for cleaning datasets
│   └── utils.py       <- Reusable utility functions
```

## Getting Started

### 1. Clone the repository

```bash
git clone <repository-url>
cd <repository-name>
```

### 2. Set up the environment

1. Duplicate `.env.example` and rename it as `.env`:

   > **Note**: If your project doesn't require environment variables, you can skip creating the `.env` file.

   ```bash
   cp .env.example .env   # Linux, macOS, Git Bash, WSL
   copy .env.example .env # Windows Command Prompt
   ```

2. **Optional: Add your project dependencies**:
   This template includes a `requirements.txt` file as a placeholder. Add the Python packages your project requires here. Example:

   ```plaintext
   pandas
   numpy
   matplotlib
   ```

> **Note**: This template is compatible with Python 3. Ensure you have Python 3 installed before proceeding.

### 3. Organize your data

- Remove `.gitkeep` files from each folder to ensure only the folders you actively intend to be tracked are included.
- Place raw files in `data/raw`.
- Use `data/raw_chunks` for large datasets split into parts.
- Place unusable data in `data/garbage` for auditing or debugging.
- Add a `README.txt` in `data/raw` to document the source of your dataset. Example content:

```plaintext
Dataset Source:
- URL: https://example.com/dataset
- Date Accessed: YYYY-MM-DD

Description:
- This dataset contains raw customer data, including demographic and transactional information.

Notes:
- The dataset is licensed under XYZ.
- Ensure compliance with data usage terms before sharing.
```

### 4. Adjust `.gitignore`

Ensure the `.gitignore` file is customized for your project needs. The template `.gitignore` includes common exclusions for:

- **Python bytecode files**: (`__pycache__/`, `*.py[cod]`)
- **Virtual environments**: (`**/venv*/`, `**/.venv*/`, etc.)
- **Logs**: (`**/logs*/`, `*.log`)
- **Database files**: (`*.db`, `*.rdb`)
- **Distribution and packaging artifacts**: (e.g., `build/`, `dist/`, `*.egg-info/`)

#### Handling the `data` and `logs` Folders

The template `.gitignore` includes rules for ignoring the `data/` and log folders:

```plaintext
# data/*

# **/logs*/
```

- By default, these rules are commented out so the `data` folder and its contents (e.g., `raw/`, `cleaned/`, `garbage/`), and the `logs` folder remain visible in the template repository.
- Uncomment the rules for `data/` and `logs/` to ignore these folders entirely, or customize further based on your project needs.

### 5. Start cleaning data

- Use Jupyter notebooks in the `notebooks` folder to explore and clean data.
- Write reusable cleaning scripts in `src/data_cleaning.py`.

> **Tip**: As your project grows, consider splitting cleaning tasks into multiple scripts in the `src` folder for better maintainability.

### 6. Log your processes

- Use the `logs` folder to store log files generated during data cleaning.
- Logging helps track the progress and identify issues during data cleaning. Example log setup in Python:

```python
import logging

logging.basicConfig(
    filename='logs/data_cleaning.log',
    level=logging.INFO,
    format='%(asctime)s - %(levelname)s - %(message)s'
)

logging.info('Data cleaning started')
logging.error('Missing values detected in column X')
```

---

This template is a starting point for your data cleaning projects. Fork the repo and expand it as your needs grow.
