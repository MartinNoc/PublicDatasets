# MIMIC-III - The Medical Information Mart for Intensive Care III

[PhysioNet: MIMIC-III Clinical Database](https://physionet.org/content/mimiciii/1.4/)

Application for access (several days) and completed training (approx. 1 - 2 days) required.

This dataset is a large publicly available dataset of de-identified electronic health records of intensive care unit (ICU) patients at a hospital in Boston, USA. The dataset includes demographic information, clinical notes, laboratory tests, vital signs, and other clinical data.
Not multi-site in hindsight

MIMIC-III is a relational database consisting of 26 tables.

[MIMIC Extract](https://github.com/MLforHealth/MIMIC_Extract): A python based package for transforming MIMIC-III data into a machine learning friendly format. *Will probably take 5-10 hours. Will require a good machine with at least 50GB RAM.*

Most promising: Google BigQuery for SQL queries and downloading data.

Todo: What is a potential prediction task with this dataset? => Look for papers that use MIMIC. As this is (one of) the largest medical database, several papers have used MIMIC.

MIMIC contains:
<ul>
<li><strong>Patient Demographics:</strong> Basic information about patients, including age, gender, ethnicity, and admission and discharge details.

<li><strong>Clinical Data:</strong> Detailed clinical data such as vital signs, laboratory test results, medications, and fluid balance.

<li><strong>Procedures:</strong> Information about procedures performed on patients during their ICU stay.

<li><strong>Diagnoses:</strong> Diagnostic codes, including International Classification of Diseases, 9th Edition.

<li><strong>Notes and Reports:</strong> Free-text notes and reports from various healthcare professionals, providing additional context and insights into patient care.

<li><strong>Imaging Data:</strong> Radiology reports and imaging studies such as X-rays, CT scans, and MRIs.

<li><strong>Ventilation Parameters:</strong> Data related to mechanical ventilation, including settings and parameters.

<li><strong>Outcomes:</strong> Information on patient outcomes, including mortality and length of stay in the ICU.