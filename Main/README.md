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

### 📊 Distribution of Layoff Counts
The distribution of layoffs is **highly right-skewed** with a skewness of **10.79**, indicating that most companies have relatively low layoff counts, while a small number of companies have extremely high layoffs.

### 📈 Descriptive Statistics
- **Mean:** 458.02  
- **Median:** 80.00  
- **Standard Deviation:** 2599.67  

 The large difference between the mean and median confirms that the data is **strongly skewed**, with a few extreme values pulling the average upward.

### ⚠️ Outlier Analysis
The boxplot shows a **significant number of upper outliers** in layoff counts. These points are identified using the IQR method.

Although they are statistically classified as outliers, they represent **real-world large-scale layoff events** rather than data errors. Therefore, they were retained to preserve the integrity of the analysis and capture meaningful business behavior.
---

## 🔍 Key Insights

###  Biggest Finding
The **USA accounted for 80.4% of all recorded layoffs worldwide**, making it the dominant contributor despite being one of the world's most developed technology markets.

###  Biggest Surprise
Although **Japan ranked #1 in average layoffs per company**, it ranked only **9th in total layoffs**. In contrast, the **USA ranked 4th in average layoffs** but had the **highest total number of employees laid off**.

###  Counterintuitive Insight
Before analyzing the data, I expected **Google** to have the largest layoffs due to its media visibility. Surprisingly, **Amazon** recorded the highest number of layoffs, while **Google ranked 7th**.

###  Recurring Pattern
Layoffs showed an **upward trend year after year**, with a dramatic surge beginning in **2022**.

###  Future Outlook
The data suggests that the post-pandemic hiring boom has ended. Since **2022, layoffs have increased roughly threefold**, indicating that technology companies may continue prioritizing restructuring and cautious hiring in the near future.

---

## ⚠️ Limitations

###  What the Data Can't Tell Us
- The data does not explain **why** layoffs occurred, such as financial performance, restructuring, mergers, or automation.

###  Dataset Completeness
- The dataset is **not guaranteed to be complete**.
- It relies on publicly reported layoff announcements and news sources, meaning some events—especially from smaller or private companies—may be missing.

###  Survivorship Bias
- Larger and well-known technology companies are more likely to have their layoffs publicly reported.
- As a result, the dataset may **overrepresent major companies** while under-representing startups and smaller firms.

###  Can These Findings Be Generalized Globally?
- **Not entirely.**
- Since **80.4% of recorded layoffs occurred in the USA**, the dataset is heavily skewed toward the U.S. technology sector.
- Therefore, the findings are more representative of **global tech companies with strong U.S. presence** than of the worldwide labor market as a whole.

---

## 🚀 Future Scope

Although this project focuses on exploratory data analysis, there are several opportunities to extend it into predictive and business-oriented applications.

### 🤖 Predict Future Layoffs
Develop machine learning models to estimate which companies are more likely to announce layoffs based on historical trends and company characteristics.

### 📈 Integrate External Economic Data
Enrich the dataset with external indicators to better understand the drivers of layoffs, including:
- Stock market performance
- Interest and inflation rates
- Venture capital funding trends
- Company financial statements
- Macroeconomic indicators (GDP growth, unemployment, etc.)

### 🌍 Interactive Dashboard
Build an interactive dashboard using **Power BI**, **Tableau**, or **Streamlit** that allows users to explore layoffs by country, company, industry, and time period.


### 🔍 Company Benchmarking
Compare companies within the same industry to identify organizations that experienced unusually high or low layoff rates relative to their peers.

---

## 🛠️ How to Run

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/Ridima28/GLOBAL-TECH-LAYOFF-ANALYSIS.git
cd GLOBAL-TECH-LAYOFF-ANALYSIS
```

### 2️⃣ Install Dependencies

```bash
pip install pandas numpy matplotlib seaborn plotly jupyter
```

