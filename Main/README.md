# 📊 Project Overview

This project presents an **Exploratory Data Analysis (EDA)** of global tech layoffs reported between **2020 and 2025**. The analysis explores workforce reduction trends across companies, industries, countries, and time to identify meaningful patterns and insights.

## 📌 Dataset

- **Source:** Kaggle – *tech_layoffs_till_2025* (community-reported layoff records)
- **Time Period:** 2020 – 2025

### Why this project?

The technology industry has experienced significant workforce reductions since 2020. This project aims to:

- Analyze how layoffs evolved over time.
- Understand the industries and companies most affected.
- Identify geographical trends in layoffs.
- Explore seasonal and yearly layoff patterns.
- Demonstrate practical data cleaning, visualization, and exploratory data analysis techniques using Python.

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook

---

# 📂 Dataset Description

### Dataset Shape

| Attribute | Value |
|-----------|------:|
| Rows | **2,412** |
| Columns | **18** |

### Dataset Columns

| Column Name | Description |
|-------------|-------------|
| `Nr` | Record identifier |
| `Company` | Company name |
| `Location_HQ` | Company headquarters location |
| `Region` | Geographic region |
| `USState` | U.S. state (if applicable) |
| `Country` | Country where layoffs occurred |
| `Continent` | Continent |
| `Laid_Off` | Number of employees laid off |
| `Date_layoffs` | Date of layoff announcement |
| `Percentage` | Percentage of workforce laid off |
| `Company_Size_before_Layoffs` | Workforce size before layoffs |
| `Company_Size_after_layoffs` | Workforce size after layoffs |
| `Industry` | Company industry |
| `Stage` | Company funding stage |
| `Money_Raised_in__mil` | Total funding raised (in millions) |
| `Year` | Year of layoff |
| `latitude` | Latitude of headquarters |
| `longitude` | Longitude of headquarters |

---

# 🧹 Data Cleaning

Data cleaning was performed to improve the quality and consistency of the dataset before analysis.

## Missing Values

The following columns contained missing values:

| Column | Missing Values |
|--------|---------------:|
| `USState` | 1 |
| `Laid_Off` | 372 |
| `Percentage` | 449 |
| `Company_Size_before_Layoffs` | 643 |
| `Company_Size_after_layoffs` | 555 |
| `Stage` | 164 |
| `Money_Raised_in__mil` | 364 |

### Handling Missing Values

- Removed the single row containing a missing value in **USState**.
- Removed rows where **both `Laid_Off` and `Percentage` were missing**, as they did not provide sufficient information for analysis.
- Remaining missing values were retained where appropriate to preserve the integrity of the original dataset.

## Duplicate Records

- **Duplicate rows found:** **5**
- All duplicate records were removed.

## Outlier Treatment

No outliers were removed because the extreme values represented genuine layoff events rather than data entry errors.

## Data Type Conversions

- Converted the **`Date_layoffs`** column from **object** to **datetime** format to enable time-series analysis.

## Feature Engineering

Two new features were created from the layoff date:

- **`Month_layoffs`** – Month of the layoff event
- **`Year_layoffs`** – Year extracted from the layoff date

These features were used for monthly and yearly trend analysis throughout the project.

---

# 📈 Exploratory Data Analysis (EDA)

The following questions were explored to better understand global layoff trends across companies, industries, countries, and time.

## Key Findings

### 📅 Which year had the most layoffs?
- **2025** recorded the highest number of layoffs.

### 📆 Which month had the highest layoff activity?
- **January** experienced the highest number of layoffs.

### 🏭 Which industry was hit the hardest overall?
- **Consumer** was the most impacted industry in terms of total layoffs.

### 📈 Which industry recovered the fastest?
- **Retail** showed the quickest recovery based on the observed layoff trends.

### 🏢 Which company laid off the most employees?
- **Amazon** had the highest number of layoffs in absolute terms.

### 📉 Which company laid off the highest percentage of its workforce?
- **Amazon** recorded the highest workforce reduction, laying off approximately **34%** of its employees.

### 🌍 Which country had the most layoffs outside the United States?
- **India** recorded the highest number of layoffs outside the U.S.

### 🇺🇸 What percentage of global layoffs occurred in the United States?
- The **United States accounted for approximately 80.3%** of all reported global layoffs.

---

## Additional Insights

### 📊 Are layoffs concentrated in a few companies or spread across many?
Layoffs are **fairly distributed across many companies**, rather than being concentrated in only a few. While **Amazon recorded the highest absolute number of layoffs**, the overall data indicates that workforce reductions affected a broad range of organizations.

### 📈 How did layoffs trend over time?
The overall trend shows a **gradual increase with periodic spikes**, rather than a single sudden surge.

- Layoffs began increasing noticeably in **2021**.
- They **peaked in 2022**.
- Layoffs declined during **2024**.
- The trend remained elevated but lower throughout **2025**.

### 📅 Is there a seasonal pattern (Q1 vs. Q4)?
Yes. The data suggests a clear seasonal pattern, with **Q4 experiencing substantially more layoffs than Q1**.

| Quarter | Months | Total Layoffs |
|---------|--------|--------------:|
| **Q1** | January – March | **27,762** |
| **Q4** | October – December | **76,373** |

**Key Observation**

- **Q4:** 76,373 layoffs
- **Q1:** 27,762 layoffs
- **Difference:** 48,611 layoffs
- **Q4 experienced approximately 2.75× more layoffs than Q1.**

This indicates that layoffs tend to increase toward the end of the year, particularly during **October and November**.

---

## 🔬 5. Statistical Analysis  
- What is the distribution of layoff counts? (skewed? normal?)
- What are mean, median, std of layoffs per company?
- Are there significant outliers? (boxplot analysis)
- Is there correlation between funding stage and layoff %?
- Is there correlation between company age and layoff severity?
- What does the rolling average trend look like over months?

---

## 💡 6. Key Insights & Findings *(most important section)*
- What was the single biggest finding?
- What surprised you in the data?
- Which insight is counterintuitive?
- What pattern repeats across years?
- What does the data suggest about the future of tech hiring?
- Example: *"Post-2022, layoffs accelerated 3× — coinciding with Fed rate hikes and end of pandemic-era hiring boom"*

---

## ⚠️ 7. Limitations
- What can't this data tell us? (e.g. total tech workforce size unknown)
- Is the dataset complete or self-reported?
- Any survivorship bias? (only big companies get reported)
- Can you generalize findings globally?

---

## 🚀 8. Future Scope *(shows DS thinking)*
- Can you predict which companies might lay off next?
- Can you build a layoff risk score per company?
- What external data could enrich this? (stock prices, interest rates, VC funding trends)
- Could NLP on news headlines add signal?

---

## 🛠️ 9. How to Run
- Requirements / dependencies
- How to clone and run the notebook
- Dataset download link

---