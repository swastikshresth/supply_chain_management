# supply_chain_management Dashboard

Step 1
### ** Import Data into SQL Data**
a. Prepare a CSV file 
b. Create table in SQL
C. Import csv into SQL (Using a XAMPP environment with Apache server and MySQL database.)

Step 2
### **ETL (Extract Transform and Load) 
**
**1. Extract**
 a. Extract the data from the source system as a csv file and import into SQL database.
 b. Ensure the daata is correctly loaded into a sql table with correct schema.

**2. Transform**
  In the transform stage, we primarily focus on cleaning the data and converting into the meaningful, insight information for analysis.
**# Data Cleaning**
1. All row header of data type should be right (define datatye in row header before upload the csv file into mysql)
2. Check duplicate values 
Queries---
    Product_Type,SKU,price,Availability,Number_Of_Products_Sold,Revenue_Generated,
	Customer_Demographics,Stock_Levels,Lead_Times,Order_Quantities,Shipping_Times,
	Shipping_Carriers,Shipping_Costs,Supplier_Name,Location,Lead_Time,Production_Volumes
	,Manufacturing_Lead_Time,Manufacturing_Costs,Inspection_Results,Defect_Rates,Transportation_Modes,Routes,Costs

3. Check Null Values
Queries--
    select sum(Product_Type is null) as Product_Type_null,
       sum(sku is null) as sku_null,
       sum(price is null) as Price_null,
       sum(Availability is null) as Availability_null,
       sum(Number_Of_Products_Sold is null) as Number_Of_Products_Sold_null,
       sum(Revenue_Generated is null) as Revenue_Generated_null,
       sum(Customer_Demographics is null) as Customer_Demographics_null,
       sum(Stock_Levels is null) as Stock_Levels_null,
       sum(Lead_Times is null) as Lead_Times_null,
       sum(Order_Quantities is null) as Order_Quantities_null,
       sum(Shipping_Times is null) as Shipping_Times_null,
       sum(Shipping_Carriers is null) as Shipping_Carriers_null,
       sum(Shipping_Costs is null) as Shipping_Costs_null,
       sum(Supplier_Name is null) as Supplier_Name_null,
       sum(Location is null) as Location_null,
       sum(Lead_Times is null) as lead_null,
       sum(Product_volumes is null) as Production_Volumes_null,
       sum(Manufacturing_Lead_Time is null) as Manufacturing_Lead_Time_null,
       sum(Manufacturing_Costs is null) as Manufacturing_Costs_null,
       sum(Inspection_Results is null) as Inspection_Results_null,
       sum(Defect_Rates is null) as Defect_Rates_null,
       sum(Transportation_Modes IS null) as Transportation_Modes_null,
       sum(Routes is null) as Routes_null,
       sum(Costs is null) as Costs_null_count from supply_chain_management

4. Remove white space
queries:- 
  update supply_chain_management set Product_Type=trim(Product_Type),
sku=trim(sku),( for all columns).

5. For checking outliers like price which is less than 0 which is impossible.
select price from supply_chain_management where price <0;
 similary other column also need to check for outliers.

# Based on Power BI dashboard for **Suplly Chain Management Dashboard**, here are detailed **insights** and **recommendations** based on each visual and KPI shown:

###** 3. Load**

**Key Insights**

**key insights and recommendations** based on Power BI **Supply Chain Performance & Demand Forecasting Dashboard**:

##  **Insights**

### Overall Supply Chain KPIs:

* **Total Revenue:** 578K – Healthy overall revenue.
* **Total Products Sold:** 46K – Indicates strong demand.
* **Total Product Volumes:** 57K – Good output capacity.
* **Manufacturing Cost:** 4.73K – Appears quite low, potentially cost-efficient or underreported.
* **Avg. Defect Rate:** 2.28% – Acceptable, but needs product-level analysis.
* **Avg. Shipping Time:** 6 days – Moderate, may impact customer satisfaction.

---

### Product Type Performance:

* **Haircare** has:

  * Highest defect rate (41.01%)
  * Highest inspection fail rate (35.02%)
  * High production volumes (\~20K)
* **Skincare**:

  * Highest revenue and products sold (20.7K units / 242K revenue)
  * Second-highest defect rate (37.08%)
* **Cosmetics**:

  * Lowest revenue and production (\~11.8K units / 162K)
  * Lowest defect rate (21.91%)

---

###  Location-Based Performance:

* **Delhi** & **Bangalore** show the **lowest order quantities and revenue**.
* **Kolkata** and **Mumbai** lead in both.

---

###  Shipping Analysis:

* **Route A** is the most costly across all modes (Air, Rail, Road, Sea).
* **Route C** is most cost-efficient.

---

###  Inventory/Stock Insights:

* Stock levels are evenly spread but slightly lower for **cosmetics**.
* Even high-performing products like **skincare** and **haircare** don’t show excess stock, indicating good inventory balance.

---

##  **Recommendations**

### 1. **Reduce Defect Rates in Haircare**

* Investigate quality control in the haircare production line.
* Train workers or upgrade machinery for better consistency.

### 2. **Optimize Shipping on Route A**

* Analyze why Route A is most expensive across all modes.
* Consider consolidating shipments or negotiating with carriers.

### 3. **Boost Sales in Low-Performing Cities**

* Target **Delhi** and **Bangalore** with localized marketing or distribution campaigns.
* Investigate if shipping time or stock issues are affecting sales there.

### 4. **Review Skincare Scaling**

* Skincare is your top-performing category in both sales and revenue.
* Consider increasing production and promotion budget for this segment.

### 5. **Reconsider Cosmetics Line Strategy**

* Lowest revenue and volume, but also lowest defect rate.
* Consider bundling with other products or repositioning to boost market reach.

### 6. **Improve Shipping Speed**

* 6-day average is acceptable but can be improved for customer satisfaction.
* Explore partnerships with faster carriers on key routes.




