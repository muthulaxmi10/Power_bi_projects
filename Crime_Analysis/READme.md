🕵️‍♂️ Crime Rate Analysis Dashboard
🎯 Objective

The main objectives of this project are:

To identify trends in criminal activity over time.

To analyze crime distribution across states, cities, and countries.

To study the relationship between suspects and victims (gender, arrest rate, etc.).

To measure arrest effectiveness and crime clearance rate.

To visualize top crime-prone locations and common crime types.

To demonstrate ETL and data modeling concepts using Power BI.

🧩 Tools & Technologies Used
Category	Tools / Technologies
Database	MySQL
Visualization	Power BI
Data Preparation	SQL Queries, Power Query
Data Source	CSV Dataset (Crime Records)
Modeling	Star Schema (Fact & Dimension Tables)
🧠 Data Modeling

A Star Schema model was created with one Fact Table and multiple Dimension Tables.

Fact Table

fact_crime → stores key measures and foreign keys to dimension tables
Columns: Crime_ID, Date_ID, Location_ID, Victim_ID, Suspect_ID, Status_ID, CrimeType_ID, Purpose_of_Crime, etc.

Dimension Tables
Table	Description
dim_date	Contains date, month, year, and time details
dim_location	Contains location info like City, State, Country
dim_victim	Victim demographic details
dim_suspect	Suspect demographic & arrest info
dim_status	Crime case status
dim_crimetype	Types of crimes committed
⚙️ Process Flow
1️⃣ Data Import

Imported dataset from CSV file into MySQL using the Import Data feature.

2️⃣ Database Design

Created tables for Fact and Dimensions.

Added Primary and Foreign Keys.

Established relationships using ALTER TABLE statements.

3️⃣ Data Cleaning

Handled missing values.

Standardized categorical values (like gender, arrest status).

Ensured consistent date formats.

4️⃣ Power BI Integration

Connected Power BI to the MySQL database.

Imported all tables.

Built a Data Model (Fact table linked to all Dimensions).

5️⃣ DAX Measures

Created measures for better analysis:

Total Crimes = COUNT(fact_crime[Crime_ID])

Total Arrests = 
CALCULATE(
    COUNT(fact_crime[Crime_ID]),
    dim_suspect[Arrest_Made] = "Yes"
)

Arrest Rate = DIVIDE([Total Arrests], [Total Crimes])

📊 Dashboard Features
Page 1: Overview Dashboard

Total Crimes Over Time (Line Chart)

Crimes by Purpose/Type (Donut Chart)

Crimes by Month (Area Chart)

Top 5 States by Crimes (Bar Chart with Top N filter)

Total Crimes, Arrests, and Clearance Rate (Cards)

Crimes by Victim Gender (Column Chart)

Interactive Slicers: Year, Country

Page 2: Deep Analysis Dashboard

Crimes by Crime_Type (Bar Chart)

Crimes by State (Top N Filter)

Crimes by Suspect Gender (Clustered Column)

Crimes by Case Status (Pie Chart)

🔄 Interactivity

Cross-Highlighting & Filtering enabled — Selecting a crime type or state updates all visuals dynamically.

Top N filters used to show top 5 states with highest crime rate.

Slicers for dynamic filtering by Year and Country (synced across pages).

📈 Insights & Findings

Certain states consistently show higher crime rates.

Arrest rates vary based on suspect demographics.

A clear seasonal pattern exists in crime frequency.

Cybercrime & Theft dominate in most regions.

Male suspects and female victims are more common statistically.

✅ Conclusion

This project successfully demonstrates:

Building a relational data model (Star Schema).

Integrating SQL with Power BI.

Using DAX for analytical measures.

Designing an interactive dashboard with cross-filtering and real-time insights.

💡 The final dashboard provides actionable intelligence on crime trends — helping analysts and agencies prioritize resources and improve public safety.
