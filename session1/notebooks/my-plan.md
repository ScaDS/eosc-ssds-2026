# Data Exploration & Validation – Coarse Plan

## 1. Define Project Context
- Clarify research questions and how the CSV data supports them.  
- Identify data owners, collection methods, and any legal/ethical constraints.

## 2. Initial Data Inspection
- Open the file to verify delimiter, encoding, and header presence.  
- Note number of rows, columns, and basic data types.

## 3. Data Quality Assessment
- **Missing values:** quantify per column and decide handling strategy.  
- **Duplicates:** detect exact or near‑duplicate records.  
- **Inconsistent formats:** check dates, categorical codes, numeric precision.  
- **Outliers:** flag extreme values for review.

## 4. Gather Metadata
- Create a data dictionary: column name → description, unit, permissible values, source.  
- Record any transformations already applied to the raw data.

## 5. Data Profiling
- Compute summary statistics (mean, median, range) for numeric fields.  
- Generate frequency tables for categorical variables.  
- Identify obvious relationships or anomalies worth deeper investigation.

## 6. Document Findings for the DMP
- **Data provenance:** origin, acquisition date, responsible parties.  
- **Quality indicators:** completeness, accuracy, consistency, and identified issues.  
- **Privacy & licensing:** any personal identifiers, consent, and reuse permissions.  
- **Storage & backup:** location, format, and backup schedule.  
- **Sharing & reuse:** conditions for external access and long‑term preservation.

## 7. Define Follow‑up Actions
- List cleaning steps (e.g., imputation, de‑duplication).  
- Highlight any additional data that may be needed.  
- Note ethical reviews or approvals required before analysis.

*This plan provides a structured roadmap for the exploratory phase and ensures that all relevant information is captured for inclusion in the Data Management Plan.*