## Exploratory Data Analysis (EDA) Findings
**Summary of the exploratory data analysis results:**

### Basic Properties
- **Dataset Shape:** The dataset contains 32,770 entries with 3 columns: `Headlines`, `Time`, and `Description`.
- **Unique Articles:** There are 32,575 unique headlines.
- **Duplicate Rows:** Identified 55 duplicate rows.
- **Invalid Time Values:** There are no invalid time values.
- **Data Types:** All columns are of `object` data type.
## Trends Over Time
Analyzed the volume of articles over time, there is a strong emphasis on geopolitical and economic events with words like "trade," "billion," "deal," and "china" frequently appearing, highlighting ongoing discussions around trade agreements and economic impact. The prevalence of days of the week suggests frequent reporting on daily events, possibly indicating regular news cycles or financial reporting. The appearance of "coronavirus" [COVID_19] which caused the pandemic, indicates a significant focus on health-related news, reflecting the widespread impact of the pandemic. Additionally, the names "trump" and "united" imply coverage related to political figures and entities, pointing toward political news being a major topic of discussion.

## TASK 2

**Goal:** *To extract company names or stock tickers from news articles, map the extracted company names to their respective stock tickers using an API or reliable dataset. A dataset from Kaggle (S&P 500 companies) is downloaded, providing a list of stock tickers with corresponding company names.*

### Data Collection
- **News Sources:**
  - News headlines and descriptions are loaded from `reuters_headlines.csv`.
  - A dataset of S&P 500 companies (`sp500_companies.csv`) is used as the mapping source.

### Named Entity Recognition (NER)
- **Model Used:**
  - SpaCy’s NER model is utilized to extract organization names from article descriptions.
- **Data Cleaning:**
  - Extracted names are cleaned to remove possessives, brackets, and quotes.

### Mapping to Tickers
- **Mapping Process:**
  - Extracted company names are mapped to S&P 500 tickers using a dictionary that includes both short and long company names.
- **Fuzzy Matching:**
  - Fuzzy matching (via `rapidfuzz`) ensures accurate mapping even with slight variations in company names.

### Final Output
- **Filtered Articles:**
  - Articles are filtered to retain only those with successfully matched tickers.
- **Resulting Dataset:**
  - The resulting dataset includes **headlines**, **descriptions**, **extracted company names**, **matched company names**, and **stock tickers**.


