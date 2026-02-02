# SCLM-479 Group Project – Demand Planning & Inventory Logic (Kingwood Case)

## 📌 Project Overview
This project focuses on demand planning and inventory management logic using a structured Excel-based approach.  
The dataset simulates a real-world case at **Kingwood**, where project-based demand, Bill of Materials (BOM), inventory levels, supplier evaluation, and safety stock decisions are integrated into one planning workflow.

Each worksheet in the Excel file represents **one specific operational task**, allowing transparent tracking from demand generation to inventory control.

---

## 📂 Repository Contents
- `Group_Project_302_Final.html` – Final rendered report (HTML)
- `README.md` – Project overview and usage instructions
- `.github/workflows/` – GitHub Actions workflow for GitHub Pages deployment
- `Kingwood_Demand_Dataset_Logic Group.xlsx` – Main Excel workbook used for analysis

---

## 📊 Excel Workbook Structure & Logic

### 1. Inventory level
**Purpose:**  
Tracks current inventory levels and standardizes units of measurement.

**Key Excel functions used:**
- `VLOOKUP()` – Retrieve unit of measurement (UOM) from the BOM sheet
- `IFERROR()` – Prevent errors when material codes are missing

**Outcome:**  
Ensures inventory quantities are comparable with material requirements.

---

### 2. Project Data
**Purpose:**  
Stores raw project-level data, including project value, timing, probability, and year.

**Key Excel functions used:**
- `SUM()` – Aggregate total project values

**Outcome:**  
Provides the base dataset for further time-based analysis.

---

### 3. Data-quarterly
**Purpose:**  
Distributes project values by quarter and month to reflect seasonality patterns.

**Key Excel functions used:**
- `SUM()` – Calculate quarterly totals
- Division formulas – Compute quarterly and monthly shares
- `AVERAGE()` – Estimate average seasonal distribution across years

**Outcome:**  
Creates a seasonality profile for demand forecasting and planning.

---

### 4. New order
**Purpose:**  
Captures new incoming orders for the planning period (e.g., 2026).

**Key Excel functions used:**
- Basic arithmetic formulas – Estimate quantities or values

**Outcome:**  
Acts as demand input for requirement calculations.

---

### 5. BOM (Bill of Materials)
**Purpose:**  
Defines material consumption per product type.

**Key Excel functions used:**
- `SUM()` – Calculate total material usage across products

**Outcome:**  
Serves as the core logic to convert product demand into material demand.

---

### 6. Supplier evaluation
**Purpose:**  
Evaluates suppliers based on multiple performance criteria.

**Key Excel functions used:**
- `AVERAGE()` – Calculate overall supplier scores

**Outcome:**  
Supports supplier selection and sourcing decisions.

---

### 7. Requirement
**Purpose:**  
Calculates total material requirements across multiple projects (A, B, C, etc.).

**Key Excel functions used:**
- `SUM()` – Aggregate material demand across all projects

**Outcome:**  
Provides a consolidated material requirement list for inventory comparison.

---

### 8. Manage stocks
**Purpose:**  
Simulates inventory consumption step-by-step across sequential project execution.

**Key Excel functions used:**
- Subtraction formulas – Deduct material usage from beginning stock
- `IF()` – Prevent negative inventory values by capping at zero

**Outcome:**  
Identifies stock shortages and critical depletion points.

---

### 9. Safety stocks
**Purpose:**  
Calculates safety stock levels based on demand volatility and supply risk.

**Key Excel functions used:**
- `SUM()` – Total demand
- Division formulas – Convert total demand into daily demand
- Multiplication formulas – Calculate safety stock using buffer days

**Logic applied:**
- Domestic materials: 7 buffer days  
- Imported materials: 14 buffer days

**Outcome:**  
Determines appropriate inventory buffers to reduce supply disruption risk.

---

## 🔁 How to Use the Excel File
1. Update material definitions or quantities in the **BOM** sheet.
2. Input or revise project data in **Project Data** or **New order**.
3. Review total material demand in the **Requirement** sheet.
4. Check inventory sufficiency and depletion sequence in **Manage stocks**.
5. Adjust buffer days and review recommended safety stock in **Safety stocks**.

---

## 🧠 Key Learning Outcomes
- Translating project-based demand into material requirements using BOM logic
- Applying Excel functions to support operational decision-making
- Understanding inventory risk through sequential stock consumption and safety stock modeling
- Structuring Excel workbooks so that each worksheet represents a clear business task
