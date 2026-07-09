# Aurora Bank: Credit Card Customer Insights & Risk Mitigation Dashboard

## 📌 Project Overview
This project delivers an enterprise-grade Business Intelligence solution for **Aurora Bank**, a fictional retail banking institution. In retail banking, profitability relies on a delicate equilibrium: aggressively driving card-based revenue through targeted marketing while stringently minimizing credit default exposure and operational friction. 

Using **Power BI**, **Power Query**, and **Python**, this project processes transaction logs, customer credit histories, and system logs to build an end-to-end analytics dashboard. The solution is structured into two distinct corporate themes to optimize storytelling and deliver actionable insights for both marketing teams and risk officers.

---

## Dashboard Architecture & Data Storytelling

The interactive dashboard is split into two specialized analytical pages, matching the dual pillars of modern commercial banking:

### Page 1: Customer Value & Marketing Strategy Analysis
Focuses on identifying growth vectors, understanding consumer behavior, and capturing untapped credit utilization opportunities.
* **Generational Spend Analytics:** Evaluates spending volume, purchase frequencies, and average ticket sizes across demographic cohorts.
* **Micro-Merchant Trends:** Pins down precisely where cardholders allocate liquidity (Money Transfers, Groceries, Fuel, etc.) to target co-branded reward partnerships.
* **Inactive Portfolio Reactivation:** Isolates high-income, credit-worthy customers holding a zero-swipe card history to design introductory cross-sell initiatives.
* **VIP Campaign Selection Modeling:** Uses a specialized filtering index to model top-tier customer subsets for premium tier-upgrades (e.g., Platinum/Infinity cards).

### Page 2: Credit Risk & Fraud Management
Focuses on shielding the bank's balance sheet from bad debt, spotting financial distress anomalies, and auditing system handshake failures.
* **Risk Optimization (Zero-Debt Segment):** Maps credit scores against Debt-to-Income (DTI) metrics to reveal an elite, entirely debt-free customer group (`DTI = 0`) prime for credit extension.
* **Critical Bad Debt & Fraud Alerts:** Flags high-exposure accounts breaching safe DTI limits (>40%), isolating extreme outliers (DTIs exceeding 2,000%) indicative of structural default or first-party application fraud.
* **Payment Pipeline Integrity Matrix:** Breaks down failed transaction codes (`Insufficient Balance`, `Bad PIN`, `Technical Glitch`) across card brands and network types to pinpoint system bottlenecks.

---

## Tech Stack & Implementation Details

* **Data Profiling & Initial Inspection:** Microsoft Excel (used for initial data screening, parsing structured text patterns, and validating numeric distributions).
* **Database Management & SQL Querying:** DBeaver Community Edition (utilized as the core database client interface to structure datasets, verify primary/foreign keys, and run relational data checks).
* **BI Platform & ETL Ingestion:** Power BI Desktop
* **Data Transformation Layer:** Power Query (M Language) for automated row mapping, handling empty variables, and typing structural formats.
* **Data Modeling:** Star Schema (configured clean dimensional fields pointing directly to granular transactional logs to optimize calculation engine performance).

### Financial & Operational Metrics Calculated:
$$\text{Average Ticket Size} = \frac{\text{Total Spend USD}}{\text{Total Transactions}}$$

$$\text{Debt-to-Income (DTI) Ratio} = \frac{\text{Total Monthly Debt Obligations}}{\text{Gross Monthly Income}} \times 100\%$$
### Financial & Operational Metrics Calculated:
$$\text{Average Ticket Size} = \frac{\text{Total Spend USD}}{\text{Total Transactions}}$$

$$\text{Debt-to-Income (DTI) Ratio} = \frac{\text{Total Monthly Debt Obligations}}{\text{Gross Monthly Income}} \times 100\%$$

---

## 📈 Key Findings & Actionable Business Insights

1. **The Mastercard Gateway Glitch:** The *Payment Pipeline Integrity Matrix* revealed that **Mastercard Debit processing accounts for a staggering 67.4% of all core technical failures (120 out of 178 total system glitches)**. 
   * *Mandate:* Core IT Infrastructure teams must immediately audit the API handshake layer specific to Mastercard debit bins to prevent transaction dropouts and secure interchange fee revenue.
2. **First-Party Fraud Detection:** The system isolated extreme distress indicators, such as Customer 1168 holding **\$242,379** in total debt, a subprime credit score of **505**, and an anomalous **DTI ratio of 2,652%**. 
   * *Mandate:* Risk Operations must implement an immediate automated credit freeze on these flagged profiles and route them to Fraud Investigation to mitigate severe loan-loss provisions.
3. **The Zero-Debt Goldmine:** A segment of **76 affluent users** maintaining strong credit scores (averaging 756, peaking at 850) was discovered to possess a **DTI ratio of exactly 0.00**, meaning they are completely debt-free.
   * *Mandate:* Product and Marketing divisions should fast-track this group for pre-approved, higher-margin retail lending products (mortgages, auto loans) with zero threat of capital degradation.

---

## 🔒 Data Governance & Privacy Compliance
Adhering to strict international banking data security frameworks, the underlying datasets were structurally managed for compliance:
* **PII Redaction:** All sensitive Personally Identifiable Information (PII) including cardholder names, phone numbers, and physical addresses was completely scrubbed and mapped to secure relational hash keys (`customer_id`).
* **Financial Obfuscation:** Debt and income aggregates were passed through numeric normalization algorithms to protect proprietary financial reporting layers while preserving data variance for analytical modeling.

---

## 🚀 Data Attribution & How to Use

1. **Source Data:** The raw transactional, marketing, operational, and credit risk data files utilized across both analytical branches in this project were retrieved from this [Google Drive Project Repository](https://drive.google.com/drive/folders/1X4Q7Ryev3UgBn-Bz6GjDoraVjRKkOe66?fbclid=IwY2xjawS6iW1leHRuA2FlbQIxMABzcnRjBmFwcF9pZBAyMjIwMzkxNzg4MjAwODkyAAEeOUM9w6BxzxNdD-M1Mp5pw691h95vpxCFkWLaCMN3bpx2_diSAd-o-1OTbbw_aem_jQejWIhZISVPBbn0DJidMw).
2. Clone this repository to your local computer.
3. Ensure you have **Power BI Desktop** and **DBeaver** installed on your system.
4. Extract the CSV source datasets into your local `Data/` directory.
5. Open `Dashboard/Aurora_Bank_Analytics.pbix` in Power BI. If the application flags broken file pathways, navigate to **Data Source Settings** inside Power Query to remap the table locations to your local folder paths.

---

## Repository Structure

```directory
├── Data/                             # Raw CSV extracts source files
│   ├── Branch 1 (Marketing & Customer Value)/
│   │   ├── Total Spending Volume by Generation.csv
│   │   ├── Total_sales_volume by merchant_category.csv
│   │   ├── Low-risk profile that rarely use credit cards.csv
│   │   └── VIP Campaign Mailing List.csv
│   └── Branch 2 (Risk & Operations)/
│       ├── Credit Score and DTI Ratio.csv
│       ├── Critical Bad Debt Aleart.csv
│       ├── Customer with low risk and High-Margin target.csv
│       └── Technical Failure Log.csv
├── Dashboard/
│   └── Aurora_Bank_Analytics.pbix     # Completed Power BI Project File
├── Reports/
│   └── Executive_Analytical_Report.md # Full Academic Business Case Report
└── README.md                          # Repository documentation
