# Pharma-RnD-Portfolio-Tracker
End-to-end BI project simulating a pharmaceutical R&amp;D analytics platform. Built a relational SQL Server database and Python data generator to track drug pipelines, clinical trials, costs, regulatory progress, and revenue forecasts. Designed for scalable ETL, analytics, and executive dashboards using the Microsoft BI stack.

<img width="1208" height="705" alt="image" src="https://github.com/user-attachments/assets/d13395e5-2481-452c-90fe-d2a85a6177e9" />


Pharma R&D Portfolio Tracker — Phase 1
Database Design & Data Generation
This repository contains Phase 1 of a larger Business Intelligence project that focuses on:
* Designing a relational database for pharmaceutical R&D pipelines
* Generating realistic synthetic data using Python
* Preparing the foundation for ETL, analytics, and dashboards
Future phases will add:
* SSIS pipelines
* SSAS analytical models
* SSRS reports
* Power BI dashboards

What’s Included
* SQL scripts for creating all core tables
  sample:
-- CLINICAL TRIALS TABLE:
  
CREATE TABLE ClinicalTrials (
    TrialID INT IDENTITY(1,1) PRIMARY KEY,
    DrugID INT FOREIGN KEY REFERENCES Drugs(DrugID),
    StageID INT FOREIGN KEY REFERENCES PipelineStages(StageID),
    TrialName NVARCHAR(150),
    Location NVARCHAR(100),
    NumberOfPatients INT,
    StartDate DATE,
    EndDate DATE,
    Result NVARCHAR(20) CHECK (Result IN ('Positive', 'Negative', 'Ongoing', 'Terminated'))
  
* Python data generator with reproducible seed
  sample:
  Table 2: Drugs
  drugs = []
  for i in range(1, NUM_DRUGS + 1):
    name = random.choice(["Onco", "Cardio", "Neuro", "Immuno", "Endo"]) + faker.lexify(text="????")
    drugs.append({
        "DrugID": i,
        "DrugName": name.capitalize(),
        "TherapeuticArea": random.choice(therapeutic_areas),
        "DrugType": random.choice(drug_types),
        "PatentStatus": random.choice(["Pending", "Granted", "Expired"]),
        "LeadScientistID": random.randint(1, NUM_SCIENTISTS)
    })
df_drugs = pd.DataFrame(drugs)

* Entity-Relationship Diagram (ERD)
  <img width="1208" height="705" alt="image" src="https://github.com/user-attachments/assets/fafc3dc9-9d7e-4f4d-9baa-0db281948ce7" />

* Sample analytical SQL queries

Tech Stack (Phase 1)
* Python (Faker, Pandas)
* SQL Server
* Relational modeling
  <img width="1208" height="705" alt="image" src="https://github.com/user-attachments/assets/0c6b1cca-64d8-4d69-8677-7f10a711e8c2" />


Roadmap
*  Database schema
*  Data generator
*  ETL with SSIS
*  Analytical model (SSAS)
*  Reporting (SSRS)
*  Dashboards (Power BI & Excel)
  <img width="1146" height="651" alt="image" src="https://github.com/user-attachments/assets/aef4717c-73d1-433b-809b-10edcc2733ad" />
  <img width="851" height="606" alt="image" src="https://github.com/user-attachments/assets/0f72e6d7-a564-4f83-97b0-37155cd9cb87" />


Authors
Hamza Karra, Nada Khalid, Asem Saeed, Mahmoud Salah
