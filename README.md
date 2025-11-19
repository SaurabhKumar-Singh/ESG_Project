# ESG_Project
# ESG Score & Grade Analytics Dashboard

**Python + Power BI | ESG Score Analysis | Industry Ranking | Data Validation**

This project combines **Python (data cleaning, validation, and exploratory analysis)** with a **Power BI ESG Dashboard** built from a dataset of 700+ publicly-listed companies.  
It analyzes **Environmental, Social, and Governance (ESG) scores and grades**, evaluates **sector-level performance**, and visualizes **company-level ESG behavior**.

---

##  Project Overview  

This project uses an open-source dataset of corporate ESG scores to:

- Clean and validate the dataset using Python  
- Standardize sectors and detect outliers  
- Compute correlation between ESG pillars  
- Perform distribution and relationship analysis  
- Build a fully interactive **Power BI ESG Dashboard**  
- Visualize industry-wise ESG performance  
- Compare E, S, G components across sectors  
- Explore grade distributions and company rankings

A PDF export of the dashboard is included in this repository.


---

## 🔍 Python Analysis Summary

### ✔ Data Cleaning & Validation  
- Removed nulls  
- Standardized **industry** names  
- Detected outliers (0 or 1000 scores)  
- Validated letter grades vs numeric scores  

### ✔ Feature Engineering  
- Added consistency checks  
- Created industry-level aggregates  
- Generated a data dictionary  

### ✔ EDA (Exploratory Data Analysis)  
- Distribution plots for E, S, G, Total ESG  
- Correlation matrix  
- Scatter plots for pillar relationships  
- Top and bottom industries  

### ✔ Key Insights  
- Strong correlation between **Environmental Score** and **Total ESG Score**  
- Governance has lower correlation but still important  
- Most companies fall into **BBB**, followed by **B**  
- Few companies achieve **A** grade  
- Utilities, Tobacco, and Industrials show strong ESG performance;  
  Packaging, Food Products, and Energy rank low.

---

## 📈 Power BI Dashboard Features

The dashboard includes:

### 🔹 **KPI Cards**  
- Avg ESG Score  
- Avg E, S, G Scores  
- Total Companies  

### 🔹 **ESG Grade Distribution**  
Visualizes number of companies in A, BBB, BB, B categories.

### 🔹 **Industry ESG Ranking**  
Average total score by industry (sorted).

### 🔹 **ESG Pillar Breakdown**  
100% Stacked Bar showing the proportion of E, S, and G across industries.

### 🔹 **Company Explorer**  
Searchable table with:
- Name  
- Sector  
- Scores  
- ESG Grade  

### 🔹 **Interactive Filters**  
- Industry  
- Company  
- ESG Grade  

---

## 📸 Dashboard Preview  


### **Main Dashboard**
![Dashboard Overview](https://github.com/SaurabhKumar-Singh/ESG_Project/blob/main/ESG_Project/dashboard_Pic.JPG?raw=true)



---

## 🧮 Key DAX Measures Used  

```DAX
Avg_ESG = AVERAGE('ESG'[total_score])
Avg_E = AVERAGE('ESG'[environment_score])
Avg_S = AVERAGE('ESG'[social_score])
Avg_G = AVERAGE('ESG'[governance_score])

Company_Count = DISTINCTCOUNT('ESG'[ticker])

Industry_Avg_ESG = AVERAGE('ESG'[total_score])

GradeSort =
SWITCH(
    'ESG'[total_grade],
    "A", 1,
    "BBB", 2,
    "BB", 3,
    "B", 4,
    99
)

![Dashboard Screenshot](images/dashboard_main.png)


