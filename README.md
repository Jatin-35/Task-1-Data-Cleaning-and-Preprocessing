# 🧹 Data Cleaning and Preprocessing: Netflix Movies and TV Shows

## 📁 Dataset
- **📌 Source**: [Netflix Movies and TV Shows](https://www.kaggle.com/datasets/shivamb/netflix-shows) from Kaggle  
- **📝 Description**: Contains information about Netflix titles including show ID, type, title, director, cast, country, date added, release year, rating, duration, genres, and description.

---

## 🧼 Cleaning Steps

### 1️⃣ Missing Values
- 🔍 Identified missing values using `df.isnull().sum()`.
- 🧑‍🎬 Filled missing `director`, `cast`, `country`, `rating`, and `duration` with `'Unknown'`.
- 🗓️ Filled missing `date_added` with the mode (most frequent date).
- ✅ Checked and ensured `title` had no missing values; added drop safety just in case.

### 2️⃣ Duplicates
- 📑 Checked for duplicates using `df.duplicated().sum()` (none found).
- 🧽 Removed any potential duplicates using `df.drop_duplicates()`.

### 3️⃣ Text Standardization
- 🔤 Converted `type` to lowercase (e.g., `'Movie'` → `'movie'`).
- 🌍 Converted `country` to title case (e.g., `'united states'` → `'United States'`).
- 🏷️ Standardized `rating` to uppercase and `listed_in` to title case.

### 4️⃣ Date Formatting
- ⏳ Converted `date_added` to datetime format.
- 📅 Formatted as `dd-mm-yyyy` for consistency.

### 5️⃣ Column Names
- ✏️ Renamed all column headers to lowercase with underscores (e.g., `Date Added` → `date_added`).

### 6️⃣ Data Types
- 🔢 Ensured `release_year` is of integer type.
- ⏱️ Extracted numeric values and units from `duration` column for possible analysis.

### 7️⃣ Outlier Check
- 📈 Checked `release_year` for unrealistic values — none found.

---

## 🛠️ Tools Used
- 🐍 Python (Pandas)
- 📓 Jupyter Notebook

---

## 📤 Output
- ✅ Cleaned dataset: `cleaned_netflix_titles.csv`
- 💻 Code notebook: `task1.ipynb`
- 📄 Original dataset: `netflix_titles.csv`

---

## 📝 Notes
- ✔️ All steps followed task guidelines using only **free and open-source tools**.
- 🔧 Choices like filling with `'Unknown'` were made to **preserve rows** for analysis while handling missing data.

