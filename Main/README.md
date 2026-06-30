## Project Overview

This project is a Exploratory Data Analysis (EDA) on global tech layoffs up to 2025.

    Dataset Source:
        Kaggle: Layoffs 2020–2025 dataset (community-reported layoff records)
        Time range: 2020 – 2025
     Why this topic?
        I chose this topic because:
        Global layoffs increased significantly after 2020
        It helps understand economic downturns, and tech industry trends
        It provides strong real-world insights into workforce dynamics
     Tools Used:
        Python
        Pandas
        Matplotlib
        Seaborn
        NumPy

---

## Dataset Description

    Shape of dataset:
        Rows: 2412
        Columns: 18
    Column Name:
        Nr                          
        Company                     
        Location_HQ                 
        Region                      
        USState                     
        Country                     
        Continent                   
        Laid_Off                    
        Date_layoffs                
        Percentage                  
        Company_Size_before_Layoffs 
        Company_Size_after_layoffs  
        Industry                    
        Stage                       
        Money_Raised_in__mil        
        Year                        
        latitude                    
        longitude       


---


## 🧹 3. Data Cleaning
- Were there missing values? How many? In which columns?
    There were missing values in->
---
    USState                          1
    Laid_Off                       372
    Percentage                     449
    Company_Size_before_Layoffs    643
    Company_Size_after_layoffs     555
    Stage                          164
    Money_Raised_in__mil           364
---
```
- How did you handle nulls - dropped or imputed?

    Row of USState with 1 null value was dropped
    Rows which have null values in both percentage and layoff, were dropped as they aren't providing any meaningful information.

- Were there duplicates? How many?

    Yes, total 5 duplicates were there

- Did you remove any outliers? Why?

    No Outliers were removed as they were real data and not fault in data entry.

- Any type conversions done? (dates, strings → numeric)

    Date_layoffs were object type. Therefore it was converted into Date-Time

- Did you engineer any new features? (e.g. layoff rate, year extracted from date)

    Yes, Month_layoffs and Year_layoffs were engineered from Date_Layoffs
```
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

## 🔬 5. Statistical Analysis *(this is what separates DS from analyst)*
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