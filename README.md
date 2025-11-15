# End-to-End-Healthcare-Data-Engineer-Project-Azure-Databricks-Data-Factory

#### 1.	Business Background
Midwest Health Alliance (MHA) is a network of 7 hospitals across the Midwest region. We face daily challenges in patient flow management, especially during high-demand periods such as seasonal flu outbreaks.
We lack a centralized, real-time data system to monitor bed occupancy, patient admission/discharge patterns, and department load.

#### 2.	Business Objectives
•	Monitoring patient admissions to minimize waiting times.

•	Identify department-level bottlenecks (e.g., Emergency, Surgery, ICU).

•	Enable gender-based and age-based KPIs for demographic insights.

•	Automate Alerts in case of failures. (incase Data Pipelines fails we need to alert the person who manages the Data Pipelines so we can fix it and make it work again)

#### 3.	Functional Requirements

1. Data Sources
   1. Real-time patient admission/discharge data from hospital registration systems.
   2. Daily batch extracts from Electronic Health Records (EHR) systems.
   3. Department metadata (capacity, staff numbers).
2. Data Processing & Storage.
   1. Store data in a Medallion architecture (Bronze → Silver → Gold).
   2. Handle schema evolution (if the schema of the dataset updates it shouldn’t breaks the data pipeline, the pipeline will adopt the new schema) when new patient attributes are introduced.
   3. Implement Slowly Changing Dimension Type 2 (SCD2) for example (the patient age changes so we are going to update the patient age, we will keep patient old data with patient age and change the status as inactive for the old one and active for the new one) for patient and department history.
3. Analytics
   1. Use Azure Synapse for analytics queries.
   2. Build dashboards in Power BI with KPIs such as:
         1. Current occupancy % by department
         2. Gender-based occupancy distribution
         3. Average length of stay per patient
4. Orchestration & Automation
   1. Use Azure Data Factory to automate:
         1. Daily batch ingestion from EHR
         2. Real-time processing triggers
         3. Gold-layer refresh for dashboards
5. Data Quality
   1. Simulate realistic dirty data issues (e.g., missing admission times, duplicate patient IDs, wrong timestamps) and handle them in Silver layer processing.
6.	Security & Compliance
      1. Role-based access control for different hospital departments. 

#### 4.	Deliverables

•	Fully functional Azure-based data pipeline.

•	Power BI dashboard connected to live Synapse queries.

•	Data quality & validation reports.

•	Full project documentation (architecture, data models, Git repo).

