# Session 2: Python Toolbelt for Data Stewards in JupyterLab

A practical, Python-based toolkit for data stewards to turn incoming project data into a
**validated, well-documented, and handover- or deposit-ready package**, using JupyterLab as the
execution and reporting environment.

Building on Session 1, we follow one deliberately messy dataset through a realistic pipeline -
**validate → report & clean → package → document & deposit** - letting the AI assistant draft the
code at each step while we read, run, and verify what it produces.

**You will learn to:** enforce a data schema with `pandera`, generate a data quality report with `fg-data-profiling`,
apply light cleaning, build a FAIR data package with `frictionless`, draft a Data Management Plan,
and optionally deposit the result to the Zenodo Sandbox for a DOI.

**Notebooks**

1. `1_toolbelt-overview` - orientation and a first look at the raw data
2. `2_data-validation` - a data contract that finds every rule violation (`pandera`)
3. `3_quality-report` - a quality report and light cleaning (`fg-data-profiling`)
4. `4_metadata-packaging` - a documented, FAIR data package (`frictionless`)
5. `5_dmp-and-deposit` *(optional)* - a Data Management Plan and an optional Zenodo deposit

*Prerequisite: Session 1, or equivalent familiarity with JupyterLab and the `bia-bob` assistant.*