# Web Scraping and Market Analysis of Smartwatches on Flipkart.  
### Web Scraping & Exploratory Data Analysis (EDA)

---

##  Project Overview

This project focuses on extracting smartwatch product data from Flipkart, cleaning and transforming the dataset, and performing Exploratory Data Analysis (EDA) to uncover pricing trends, brand performance, rating distribution, and sponsorship impact.

The workflow consists of two major stages:

1. Web Scraping & Data Preprocessing  
2. Exploratory Data Analysis & Visualization  

---

##  Technologies Used

- Python  
- BeautifulSoup  
- Requests  
- Pandas  
- NumPy  
- Matplotlib
- Seaborn  
- Regular Expressions (re)  

---

#  Stage 1: Web Scraping & Data Preprocessing

##  Data Collection

- Scraped **100 pages** of Flipkart smartwatch listings  
- Extracted the following fields:
  - Product Name  
  - Colour  
  - Flipkart Assured Status  
  - Sponsored Status  
  - Price  
  - Original Price  
  - Discount  
  - Promotion Tag  
  - Ratings  
  - Reviews  
  - Page Number  

- Total records collected: **1000 rows**

---

##  Data Cleaning & Feature Engineering

###  Handling Missing Values

- Filled missing values using **mode**
- Ensured zero null values after cleaning

###  Feature Engineering

Created new structured features:

- **Brand** → Extracted from Product Name using regex  
- **Size** → Extracted from Colour field  
- **Strap_color** → Cleaned and extracted from Colour  
- **Price_category** → Created using price bins:

| Category       | Price Range (₹) |
|---------------|------------------|
| Budget        | 0 – 2000        |
| Mid-Range     | 2000 – 5000     |
| Premium       | 5000 – 10000    |
| Luxury        | 10000 – 50000   |
| Ultra-Luxury  | > 50000         |

###  Data Type Conversion

- Removed ₹ symbol and commas  
- Converted:
  - Price → `int`
  - Original_price → `int`
  - Ratings → `float`
  - Reviews → `int`

### Final Dataset Structure

Final structured dataset columns:

- Brand  
- Strap_color  
- Size  
- Flipkart_assured  
- Sponsored  
- Page_num  
- Price  
- Original_price  
- Discount  
- Price_category  
- Ratings  
- Reviews  
- Promotion_tag  

Final cleaned dataset size: **994 rows**

---

# Stage 2: Exploratory Data Analysis (EDA)

---

##  Univariate Analysis

### Price Distribution

- Mean Price ≈ ₹2155  
- Median Price ≈ ₹1299  
- Strong right-skewed distribution  
- Outliers detected using IQR method  

###  Top Brands by Volume

- Goboult  
- Boat  
- Fire  
- Noise  
- Gamesir  

###  Ratings Distribution

- Most ratings between **3.8 – 4.5**
- Majority clustered around 4.0+

###  Top Strap Colors

- Black  
- Silver  
- Green  
- Pink  
- Blue  

---

##  Bivariate Analysis

###  Price Category vs Ratings

<img width="1026" height="764" alt="image" src="https://github.com/user-attachments/assets/7c318da3-6827-4c8c-b64f-be2541eddb6a" />


- Higher price categories show slightly higher rating stability  
- Ultra-Luxury products maintain strong rating consistency  

###  Price vs Reviews

<img width="833" height="592" alt="image" src="https://github.com/user-attachments/assets/0c5edceb-ca60-4721-89e7-509d7a97b1df" />


- No strong linear relationship  
- Some budget products have extremely high review counts  

###  Sponsored vs Flipkart Assured

- Many sponsored products are Flipkart Assured  
- Sponsorship improves visibility but does not strongly impact ratings  

---

##  Outlier Analysis

Using IQR method:

Premium brands contributing to high-end outliers:

- Apple  
- Samsung  
- Google  
- Amazfit  

---

## Correlation Analysis

Correlation insights:

- Price & Original Price → Strong positive correlation (~0.6)  
- Ratings & Price → Moderate positive correlation (~0.29)  
- Reviews & Price → Weak negative correlation (~ -0.12)  

Key takeaway:
Higher price does not guarantee more reviews.

---


---

#  Key Insights

1. Majority of products fall under the **Budget** category  
2. A few brands dominate the smartwatch segment  
3. Ratings are consistently around 4.0 across categories  
4. Premium pricing does not strongly correlate with review volume  
5. Sponsorship increases visibility but not rating performance  

---

# Conclusion

This project demonstrates:

- End-to-end data pipeline creation  
- Real-world web scraping  
- Data cleaning & transformation  
- Feature engineering  
- Statistical analysis  
- Data visualization  
- Business insight extraction  

It provides a complete workflow from raw web data to actionable market insights in the smartwatch industry.

---

