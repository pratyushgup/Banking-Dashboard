# Banking-Dashboard
A Detailed Power Bi Dash Board and Python Data Visualization about Banking Data 

# 🏦 Banking Risk Analytics Dashboard using Power BI

## 📌 Problem Statement

The project aims to develop a basic understanding of **risk analytics in banking and financial services**. It focuses on how data can be utilized to minimize the risk of financial loss, especially during customer loan approvals.

## 💡 Solution

An interactive **Power BI dashboard** was developed to assist banks in decision-making. By analyzing various aspects of the applicant's financial profile, the dashboard helps predict whether a client is likely to repay a loan. Based on these insights, loans can be approved or declined, reducing risk and improving efficiency.

## 📂 Dataset Overview

The dataset includes multiple interrelated tables containing bank and client details. These tables are connected through primary and foreign keys.

### Tables Included:
- **Banking Relationship**
- **Client-Banking**
- **Gender**
- **Investment Advisor**
- **Period**

## 🧹 Data Cleaning & Transformation

Several transformations and calculated columns were created:
- `Engagement Timeframe`: Duration of client’s engagement with the bank.
- `Engagement Days`: Days since the client joined the bank.
- `Income Band`: Binned income values (`Low`, `Mid`) based on estimated income.
- `Processing Fees`: Derived based on `Fee Structure` values.

## 🧮 DAX Calculations & Measures

### 📏 Calculated Columns & Measures:

- **Total Clients**  
  `= DISTINCTCOUNT('Clients - Banking'[Client ID])`

- **Total Loan**  
  `= [Bank Loan] + [Business Lending] + [Credit Cards Balance]`

- **Bank Loan**  
  `= SUM('Clients - Banking'[Bank Loans])`

- **Business Lending**  
  `= SUM('Clients - Banking'[Business Lending])`

- **Total Deposit**  
  `= [Bank Deposit] + [Savings Account] + [Foreign Currency Account] + [Checking Accounts]`

- **Total Fees**  
  `= SUMX('Clients - Banking', [Total Loan] * 'Clients - Banking'[Processing Fees])`

- **Engagement Days**  
  `= DATEDIFF('Clients - Banking'[Joined Bank], TODAY(), DAY)`

- **Income Band (SWITCH Example)**  
  ```DAX
  Income Band = SWITCH(
    TRUE(),
    'Clients - Banking'[Estimated Income] < 100000, "Low",
    'Clients - Banking'[Estimated Income] < 300000, "Mid",
    "High"
  )
📊 Dashboards Created
Home

Loan Analysis

Deposit Analysis

Banking Overview

Client Summary

📈 Key KPIs Displayed
Total Clients

Total Loan

Total Deposits

Bank Loans

Business Lending

Credit Card Balance

Processing Fees

Engagement Duration

Foreign Currency Amount

Checking and Savings Account Amounts

✅ Conclusion
Power BI enables banks to leverage powerful visualizations and KPIs for:

Better loan approval strategies.

Understanding client demographics and account behaviors.

Identifying high-risk clients and reducing loan defaults.

🚀 Future Enhancements
Add predictive analytics using Power BI and Python integration.

Introduce scoring models for better client segmentation.

Expand insights across multiple branches or geographies.

📎 Project Requirements
Power BI Desktop (latest version)

Cleaned Dataset (Excel/CSV format)

Basic knowledge of DAX functions

📬 Contact
Created by: Pratyush Gupta
📍 Prayagraj, India
📞 7233020875


