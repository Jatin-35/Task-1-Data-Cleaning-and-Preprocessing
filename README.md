# Data Cleaning and Preprocessing: Netflix Movies and TV Shows

## Dataset
- **Source**: *Netflix Movies and TV Shows* from Kaggle ([link](https://www.kaggle.com/datasets/shivamb/netflix-shows)).
- **Description**: Contains information about Netflix titles, including show ID, type, title, director, cast, country, date added, release year, rating, duration, genres, and description.

## Cleaning Steps
1. **Missing Values**:
   - Identified missing values using `df.isnull().sum()`.
   - Filled missing `director`, `cast`, `country`, `rating`, and `duration` with 'Unknown'.
   - Filled missing `date_added` with the mode (most frequent date).
   - No missing `title` values, but included a check to drop any.

2. **Duplicates**:
   - Checked for duplicates using `df.duplicated().sum()` (none found).
   - Removed duplicates using `df.drop_duplicates()`.

3. **Text Standardization**:
   - Converted `type` to lowercase (e.g., 'Movie' to 'movie').
   - Converted `country` to title case (e.g., 'united states' to 'United States').
   - Standardized `rating` to uppercase and `listed_in` to title case.

4. **Date Formatting**:
   - Converted `date_added` to datetime and formatted as `dd-mm-yyyy`.

5. **Column Names**:
   - Renamed columns to lowercase with underscores (e.g., `date_added` to `date_added`).

6. **Data Types**:
   - Ensured `release_year` is integer.

7. **Outliers**:
   - Checked `release_year` for unrealistic values (none found).

## Tools Used
- Python (Pandas)
- Jupyter Notebook

## Output
- Cleaned dataset: `cleaned_netflix_titles.csv`
- Code: `task1.ipynb`
- Original dataset: `netflix_titles.csv`

## Notes
- All steps followed the task guidelines, using free tools only.
- Decisions (e.g., filling with 'Unknown') were made to preserve data for analysis while handling missing values.
