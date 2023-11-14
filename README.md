# OPTIMAL master dataset documentation
### Version: 0.1


DExtER prints one line per patient for new data extractions, for any additional baseline/outcome variables and time-series data. Many of the data fields printed carry a prefix (and sometimes a suffix as well) to help users easily identify what type of variables they are. Sections below provide a detailed overview of the methodology used for data extraction, the codelists used and the column description.

## :information_source: Data Audit

**NOTE**

* Please do not copy the data to your local device. Mount the RDS drive and then read it to memory. See here for how to mount: [mac](https://intranet.birmingham.ac.uk/it/teams/infrastructure/research/bear/research-data-service/rds/connecting-to-the-rds-via-macos.aspx), [windows](https://intranet.birmingham.ac.uk/it/teams/infrastructure/research/bear/research-data-service/rds/connecting-to-rds-via-windows.aspx), [linux](https://intranet.birmingham.ac.uk/it/teams/infrastructure/research/bear/research-data-service/rds/connecting-to-rds-via-linux.aspx)

* The user access to data is timestamped logged and accessible to project owner only. 


## Database Sources and Linkage
#### Database
| Name      | Build version | Last collection date |
|:----------|--------------:|---------------------:|
|CPRD AURUM | May, 2022     | 31st April, 2022     |

#### Linked database
| Name    | Linked to  | Build date  |
|:--------|-----------:|------------:|
|IMD data | CPRD AURUM |             |

## Methodology

### Study design

The dataset consist of a population-based cohort study recruited from general practices that contribute data to the Clinical Practice Research Datalink (CPRD) Aurum database. CPRD is a real-world research service supporting retrospective and prospective public health and clinical studies. CPRD is jointly sponsored by the Medicines and Healthcare Products Regulatory Agency and the National Institute for Health Research (NIHR), as part of the Department of Health and Social Care. CPRD collects anonymised patient data from a network of general practitioners (GP) across the UK. Primary care data are linked to a range of other health-related data to provide a longitudinal, representative UK population health dataset. The data in CPRD Aurum encompass 40 million research acceptable patients, including 13 million currently registered patients.

 CPRD data is linked to hospital episode statistics (HES) records and Indices of miltiple deprivations (IMD) records.

### Population and setting

Eligible practices and participants are identified from the CPRD Aurum database following data extraction using the Data Extraction for Epidemiological Research tool (DExtER). Participants selected in the study are actively registered from 1 January 2005 and have at least 12 months of data prior to 1 January 2005. The study end date was 30 May 2022. Patients aged from 0 to 115 year(s)at the start of the study were included. We collected data on patient socio-demographic factors (age, sex, ethnic group, socioeconomic status and lifestyle information) and a comprehensive list of comorbidities, treatments, physical measurements and lab results.

### Codelist

[Google Docs](https://docs.google.com/spreadsheets/d/19wnSlMl_UrgHRuSq7kc1dCIx0A6UGwYvXbS2Y-VKSpw/edit#gid=932103784)



## Table One
|                     |                        | Overall          | mortality (0)    | mortality (1)    |
|---------------------|------------------------|------------------|------------------|------------------|
| n                   |                        | 28121517         | 26492417         | 1629100          |
| sex, n (%)          | F                      | 14278868 (50.8)  | 13451088 (50.8)  | 827780 (50.8)    |
|                     | I                      | 683 (0.0)        | 674 (0.0)        | 9 (0.0)          |
|                     | M                      | 13841966 (49.2)  | 13040655 (49.2)  | 801311 (49.2)    |
| age, median [Q1,Q3] |                        | 30.5 [18.7,47.1] | 29.4 [17.3,43.5] | 73.5 [62.5,82.5] |
| ethnicity, n (%)    | ASIAN                  | 2267997 (8.1)    | 2232947 (8.4)    | 35050 (2.2)      |
|                     | BLACK                  | 1156866 (4.1)    | 1134329 (4.3)    | 22537 (1.4)      |
|                     | MISSING                | 8058247 (28.7)   | 7400737 (27.9)   | 657510 (40.4)    |
|                     | MIXED                  | 485838 (1.7)     | 480679 (1.8)     | 5159 (0.3)       |
|                     | OTHER                  | 422374 (1.5)     | 418678 (1.6)     | 3696 (0.2)       |
|                     | WHITE                  | 15730195 (55.9)  | 14825047 (56.0)  | 905148 (55.6)    |
| country, n (%)      | E                      | 28025034 (99.7)  | 26402380 (99.7)  | 1622654 (99.6)   |
|                     | N                      | 96483 (0.3)      | 90037 (0.3)      | 6446 (0.4)       |
| health_auth, n (%)  | East Midlands          | 752201 (2.7)     | 716400 (2.7)     | 35801 (2.2)      |
|                     | East of England        | 1129094 (4.0)    | 1055906 (4.0)    | 73188 (4.5)      |
|                     | London                 | 6678166 (23.8)   | 6466952 (24.4)   | 211214 (13.0)    |
|                     | North East             | 765091 (2.7)     | 702461 (2.7)     | 62630 (3.8)      |
|                     | North West             | 4667234 (16.6)   | 4318755 (16.3)   | 348479 (21.4)    |
|                     | Northern Ireland       | 96483 (0.3)      | 90037 (0.3)      | 6446 (0.4)       |
|                     | South East             | 5639663 (20.1)   | 5301087 (20.0)   | 338576 (20.8)    |
|                     | South West             | 3258979 (11.6)   | 3050066 (11.5)   | 208913 (12.8)    |
|                     | West Midlands          | 4118374 (14.7)   | 3838944 (14.5)   | 279430 (17.2)    |
|                     | Yorkshire & The Humber | 990740 (3.5)     | 927869 (3.5)     | 62871 (3.9)      |
| IMD, n (%)          | MISSING                | 2442913 (8.7)    | 2323746 (8.8)    | 119167 (7.3)     |
|                     | 1.0                    | 4789813 (17.0)   | 4495980 (17.0)   | 293833 (18.0)    |
|                     | 2.0                    | 4981882 (17.7)   | 4671058 (17.6)   | 310824 (19.1)    |
|                     | 3.0                    | 5072397 (18.0)   | 4777996 (18.0)   | 294401 (18.1)    |
|                     | 4.0                    | 5650727 (20.1)   | 5354077 (20.2)   | 296650 (18.2)    |
|                     | 5.0                    | 5183785 (18.4)   | 4869560 (18.4)   | 314225 (19.3)    |

## Data structure and conventions
### Data Types
Each column/variable in the extracted datasets can be classified into 4 data types. Categorical, text, continuous and Date/Time. The Date/Time in DExtER works with the ISO 8601 format, which is (yyyy-MM-dd) for any date and (yyyy-MM-dd hh:mm: ss.sss) for any timestamp.

### Structure of the extracted dataset

#### Practice information 

| Column name    | Description                                                                                               | Data type  |
|:---------------|:----------------------------------------------------------------------------------------------------------|:-----------|
|PRACTICE_ID     | The unique ID assigned to each practice.                                                                  | Text       |
|COUNTRY         | The country code in which the practice resides.                                                           | Categorical|
|STANDARD_DATE1  | This is a dummy variable set to 01-01-2005. CPRD will provide UPTO_STANDARD_DATE for AURUM in the future. | Date       |
|COLLECTION_DATE | This is the last time data was collected from the practice                                                | Date       |
|HEALTH_AUTH     | The health authority region the practice belongs to.                                                      | Categorical|

#### Patient information


| Column name        | Description                                                                                               | Data type  |
|:-------------------|:----------------------------------------------------------------------------------------------------------|:-----------|
|PRACTICE_PATIENT_ID | The unique key that identifies a single patient.                                                          | Text       |
|PATIENT_ID          | The ID of the patient (may not be unique).                                                                | Text       |
|START_DATE          | This is the patient start date. It is defined as the **latest** of the following: <br/> 1. Vision or Computerization date. <br/> 2. Acceptable Mortality Reporting(AMR) date. <br/> 3. Patient registration date. <br/> 4. Study start date. <br/> 5. Date on which patient becomes eligible for the study based on age restrictions(if any).                                                                                     | Date       |
|END_DATE            | This is the patient end date. It is defined as the **earliest** of the following: <br/> 1. Practice collection date. <br/> 2. Patient transfer date. <br/> 3. Patient death date. <br/> 4. Study end date. <br/> 5. Maximum age(115 years by default) until which patient is eligible to participate in the study.                                                                                                        | Date       |
|EXPOSURE            | The clinical code of the primary exposure.                                                                | Text       |
|INDEX_DATE          | The date on which the patient follow-up starts.                                                           | Date       |
|DEATH_DATE          | The date on which the patient had died.                                                                   | Date       |
|YEAR_OF_BIRTH       | Year of birth of the patient for adults. For children below 15 years of age the month of birth is also provided.                                                                                                                                                        | Date       |
|SEX                 | Biological sex of the patient.                                                                            | Categorical|
|REGISTRATION_DATE   | The date on which the patient registered to the practice.                                                 | Date       |
|TRANSFER_DATE       | The date on which the patient transferred out of the practice.                                            | Date       |
|ETHNICITY           | Ethnicity of the patient identified using particular clinical codes.                                      | Categorical|
|REGISTRATION_STATUS | This indicates the registration status of the patient to the practice.                                    | Categorical|
|IMD                 | Indices of multiple deprivation  (essentially a measure of poverty).                                      | Categorical|

#### Baseline information
| Column name                    | Description                                                                                                          | Data type  |
|:-------------------------------|:---------------------------------------------------------------------------------------------------------------------|:-----------|
| B_MEDI:CONDITION_NAME:0                           | column for baseline diagnosed of a condition and records the code.                                | Text       |
| BD_MEDI:CONDITION_NAME:0                          | date column for a condition to record when the diagnosis was made.                                | Date       |

## Publications
1. Cooper, J., Nirantharakumar, K., Crowe, F., Azcoaga-Lorenzo, A., McCowan, C., Jackson, T., Acharya, A., Gokhale, K., Gunathilaka, N., Marshall, T. and Haroon, S., 2023. Prevalence and demographic variation of cardiovascular, renal, metabolic, and mental health conditions in 12 million English primary care records.
