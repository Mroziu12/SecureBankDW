# SecureBankDW — Data Warehouse Project (CV-ready summary)

Project summary
- End-to-end data warehouse for a sample banking system: relational staging, ETL pipelines, and an OLAP cube for analytics.
- Designed to support reporting on loan applications, instalment payments, credit takers and employee advisors.

Responsibilities & contributions
- Designed star-schema dimensional model (dimensions: Employee, Credit Taker, Date, Junk_*; fact tables: Loan_Application_Made, Instalment_Payment).
- Implemented ETL using SSIS: created Initial.dtsx (environment setup / seed data) and Package1.dtsx (dimension & fact loads).
- Implemented Slowly Changing Dimension (SCD Type 2) handling, data cleansing and enrichment (age groups, account-balance levels).
- Built OLAP model in SSAS: Data Source View, dimension (.dim), cube (.cube) with measures, MDX calculations and KPI definitions.
- Integrated heterogeneous sources: CSV questionnaires + OLTP database; implemented merges, joins and incremental updates.

Key technical components
- ETL: LoadETL/Initial.dtsx, LoadETL/Package1.dtsx — Data Flow tasks using Aggregate, Derived Column, Data Conversion, Merge Join, Union All, OLE DB Command, Slowly Changing Dimension.
- Data model: DWSecureBankProject/*.dim, DWSecureBankProject/SecureBankDW.dsv — dimensional definitions and DSV.
- OLAP: DWSecureBankProject/SecureBankDW.cube — measures, MDX scripts and KPIs (e.g., Defaulted To Granted Ratio, Granted Loans per Year).
- Data sources: questionnaires_A.csv / questionnaires_B.csv and OLTP database (connection strings editable in SSIS connection managers).

Technologies
- SQL Server, T-SQL
- SSIS (SQL Server Integration Services) — ETL pipelines
- SSAS (SQL Server Analysis Services) — cube design, MDX, KPI
- Visual Studio 2022 with __SQL Server Data Tools (SSDT)__
- CSV, OLE DB providers

Select CV bullet points (copy/paste)
- Designed and implemented a data warehouse for a banking domain: star schema, ETL pipelines (SSIS) with SCD Type 2 and an OLAP cube (SSAS) with MDX and KPIs.
- Developed SSIS packages to integrate CSV and OLTP data, implementing data enrichment, deduplication and history tracking.
- Created SSAS cube with aggregated measures and business KPIs to support executive reporting and risk monitoring.

Notable implementation details
- SCD Type 2 used to preserve history for dimensions (Customer / Employee).
- MDX members include aggregated business metrics: Number of Granted Loans, Number of Defaulted Loans, Average Loan Amount, Average Risk Score.
- Some SSIS components perform per-row updates via OLE DB Command; for high-volume production scenarios these should be replaced with set-based operations (MERGE).

Repository
- GitHub: https://github.com/Mroziu12/SecureBankDW
- Local clone (example): C:\Users\mmroz\OneDrive\Desktop\2Studies\PG\4sem\DW\DWSecureBankProject2 (branch: master)

If you want, I can generate a one‑line project summary for the top of your CV or a 2–3 sentence elevator pitch tuned for job applications.
