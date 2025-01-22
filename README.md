# Drug Combo dataset

This repository contains the manual curation of published Phase I anticancer drug trials for Drug Combo.

## Data Source

Publications from PubMed search.

## Data curation guideline

[Data Curation Guideline](https://www.protocols.io/view/mtd-dlt-data-curation-protocol-b3ieqkbe) depicts how the data was curated from the publications. In this guideline, some examples are provided to demonstrate where the required data elements can be found in the papers. For example, the dose levels can be found in the figures or some paragraphs.

## Data Files

| File Name          | Description                                                                                                                                        |
| ------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| trial.csv          | Some general information about the trials, including PMID, Trial Registed number, cancer subtypes, trial recruitment criteria.                     |
| drug.csv           | The drug used in the trial, inclduing name, formula, and administration route. **Please note: There is no information about doing it in the file." |
| schema.csv         | The statistical design of the trial                                                                                                                |
| dlt_definition.csv | How dose-limiting toxicity (DLT) is defined in the trials                                                                                          |
| dose_level.csv     | Detailed designed dosing information                                                                                                               |
| mtd.csv            | Maximum Tolerated Dose (MTD)                                                                                                                       |
| observed_dlt.csv   | Reported DLTs in the publications                                                                                                                  |


## Data Dictionary

### trial.csv

| Column          | Description                                                                                  |
| --------------- | -------------------------------------------------------------------------------------------- |
| PMID            | PubMed unique identifier. **Files can be linked by PMID**                                    |
| NCTID           | Registration ID, typically is a NCT ID (clinicaltrials.gov)                                  |
| Trial_Type      | Indictior of a single drug trial or a drug combination trial. **Assigned by data curators**. |
| protocol        | If a detailed trial protocol is provided with the publication.                               |
| population      | Cancer subtype involved in the trial                                                         |
| Trial_Inclusion | Trial inclusion criteria                                                                     |
| Trial_Exclusion | Trial exclusin criteria                                                                      |
| DLT_EVA         | Time window for DLT evluation                                                                |
| comments        | Addtional info by the data curators                                                          |
### drug.csv

| Column      | Description                                                                             |
| ----------- | --------------------------------------------------------------------------------------- |
| PMID        | PubMed unique identifier. **Files can be linked by PMID**                               |
| NCTID       | Registration ID, typically is a NCT ID (clinicaltrials.gov)                             |
| CombnID     | A random number to differentiate multiple drug combinations or drug dosing in one trial |
| Drug_Name   | Drug name (e.g., brand name, generic name, or internal name)                            |
| Admin_Route | Drug administration route. `i.v. - Intravenous` `sc - Subcutaneous`                     |
| Dose_Form   | Drug formula                                                                            |
| comments    | Addtional info by the data curators                                                     |
### schema.csv

| Column     | Description                                                                                                                          |
| ---------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| PMID       | PubMed unique identifier. **Files can be linked by PMID**                                                                            |
| NCTID      | Registration ID, typically is a NCT ID (clinicaltrials.gov)                                                                          |
| ES         | `Escalation - starting from a lower dose and increase the dose`<br>`De-escalation - starting from a higher dose and reduce the dose` |
| DesignType | Statistical design method                                                                                                            |
| schema     | How to reach the maximum dose                                                                                                        |
### dlt_definition.csv

| Column        | Description                                                                                                                 |
| ------------- | --------------------------------------------------------------------------------------------------------------------------- |
| PMID          | PubMed unique identifier. **Files can be linked by PMID**                                                                   |
| NCTID         | Registration ID, typically is a NCT ID (clinicaltrials.gov)                                                                 |
| CombnID       | A random number to differentiate multiple drug combinations or drug dosing in one trial                                     |
| DLT_Name      | A dose-limiting toxicity term or expression                                                                                 |
| Grade         | The severity of the DLT                                                                                                     |
| Duration      | When do adverse drug events (ADE) occur, and how long do they last? These can be defined as dose-limiting toxicities (DLT). |
| DLT_Exculsion | If this DLT_Name should be excluded from DLT                                                                                |
| comments      | Addtional info by the data curators                                                                                         |
### dose_level.csv

| PMID       | PubMed unique identifier. **Files can be linked by PMID**                               |
| ---------- | --------------------------------------------------------------------------------------- |
| NCTID      | Registration ID, typically is a NCT ID (clinicaltrials.gov)                             |
| CombnID    | A random number to differentiate multiple drug combinations or drug dosing in one trial |
| Drug_Name  | Drug name (e.g., brand name, generic name, or internal name)                            |
| Dose_Level | An identifier to differentiate distinct doses in one trial.                             |
| Dose_Vaule | The number of dose                                                                      |
| Dose_Unit  | Dose unit                                                                               |
| Frequency  | How many times is the drug used in one day or one week                                  |
| Schedule   | Which days is the drug administrated in one cycle or one week                           |
| comments   | Addtional info by the data curators                                                     |
### mtd.csv

| NCTID     | Registration ID, typically is a NCT ID (clinicaltrials.gov)                             |
| --------- | --------------------------------------------------------------------------------------- |
| CombnID   | A random number to differentiate multiple drug combinations or drug dosing in one trial |
| Drug_Name | Drug name (e.g., brand name, generic name, or internal name)                            |
| MTD_Value | The number of dose                                                                      |
| MTD_Uint  | Dose unit                                                                               |
| Frequency | How many times is the drug used in one day or one week                                  |
| Schedule  | Which days is the drug administrated in one cycle or one week                           |
| comments  | Addtional info by the data curators                                                     |
### observed_dlt.csv

| PMID               | PubMed unique identifier. **Files can be linked by PMID**                               |
| ------------------ | --------------------------------------------------------------------------------------- |
| NCTID              | Registration ID, typically is a NCT ID (clinicaltrials.gov)                             |
| CombnID            | A random number to differentiate multiple drug combinations or drug dosing in one trial |
| DLT                | The DLT occured on the participants                                                     |
| Grade              | The severity of the DLT                                                                 |
| Duration           | How long does DLT last?                                                                 |
| At_level           | The dose the participants take for the DLT                                              |
| Observed_Frequency | How many participants have the DLT                                                      |
| Total              | The total number of participants at the sepcific dose                                   |
| Occurence          | Exact day the DLT occurs                                                                |
| comments           | Addtional info by the data curators                                                     |
| combined_dose_info | The detailed dose info mapped from dose_lvel.csv                                        |
|                    |                                                                                         |


## License

This dataset is licensed under the [MIT License](LICENSE).

## Citation

If you use this dataset, please cite it as follows:

Lei Wang, Lai Wei, Shijun Zhang, Lijun Cheng, Aditi Shendre, Williams Carson, James L. Chen, Dwight Owen, Megan Gregory, Lang Li; An Informatics Bridge to Improve the Design and Efficiency of Phase I Clinical Trials for Anticancer Drug Combinations. Cancer Research Communications 2 September 2022; 2 (9): 929–936. https://doi.org/10.1158/2767-9764.CRC-22-0160

## Contact

For any questions, please contact Lei Wang at Lei.Wang2@osumc.edu.

