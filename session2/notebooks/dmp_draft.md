# Data Management Plan – Dataset Overview

## 1. Data summary
- **Content**: Biological field samples of penguins, each record containing *species*, *island*, *collection date*, *body mass*, *flipper length* and *sex*.  
- **Size**: Approximately 180 records.  
- **Format**: CSV file.  
- **Provenance**: The raw CSV was handed over from a research project and subsequently cleaned and validated by the data steward.  
- **Validation**: Validation is performed with a **pandera** schema (`data_schema.yml`) that enforces data types, controlled vocabularies for *species*, *island* and *sex*, value ranges for quantitative fields, and a unique `sample_id`.  
- **Quality assurance**: A profiling report has been generated. Known issues—missing required values and a few impossible/out‑of‑range measurements—are documented and have been flagged back to the data provider; no values were silently altered.  
- **Packaging**: The dataset is bundled as a **Frictionless Data Package** (`datapackage.json`) that includes a data dictionary and accompanying metadata.

## 2. FAIR data

### Findable
- The data package will be deposited in **Zenodo**, which mints a **DOI** that serves as a persistent identifier (PID).  
- Metadata describing the dataset (title, authors, abstract, keywords, schema information) are embedded in the `datapackage.json` and registered with Zenodo, ensuring discoverability through standard catalogues.

### Accessible
- The dataset will be openly accessible via Zenodo’s web interface using the DOI. No authentication is required.  
- The open CSV format and the Frictionless Data Package enable direct download and programmatic access (e.g., via Zenodo’s API).  
- The chosen licence (**CC‑BY‑4.0**) guarantees that anyone can retrieve and reuse the data provided proper attribution is given.

### Interoperable
- Data are stored in **CSV**, a universally readable format.  
- The accompanying **Frictionless Table Schema** and the `data_schema.yml` pandera schema define field types, controlled vocabularies, and value constraints, ensuring that the data can be interpreted by diverse tools.  
- Controlled vocabularies for *species*, *island* and *sex* are explicitly listed, facilitating semantic interoperability.

### Reusable
- The **CC‑BY‑4.0** licence clearly states reuse conditions (attribution).  
- Comprehensive documentation is provided: a data dictionary (within the Frictionless Data Package), the pandera validation schema, and the profiling report that records data quality and remaining issues.  
- Provenance is traceable from the original raw CSV through the cleaning and validation steps performed by the data steward.  
- All known quality issues are openly documented, allowing downstream users to assess suitability and to request clarification if needed.

## 3. Storage & backup (short note)
- The dataset and all associated files (CSV, `datapackage.json`, `data_schema.yml`, profiling report) are maintained under **version control** (e.g., Git) in a repository that also serves as the submission source for Zenodo.  
- Zenodo provides long‑term preservation services; therefore the repository functions as the primary backup and preservation platform.

## 4. Licensing (short note)
- The dataset is released under the **Creative Commons Attribution 4.0 International (CC‑BY‑4.0)** licence, permitting unrestricted reuse, distribution, and adaptation provided that appropriate credit is given to the original creators.