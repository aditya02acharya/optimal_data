# OPTIMAL master dataset documentation
### Version: 0.1


DExtER prints one line per patient for new data extractions, for any additional baseline/outcome variables and time-series data. Many of the data fields printed carry a prefix (and sometimes a suffix as well) to help users easily identify what type of variables they are. Sections below provide a detailed overview of the methodology used for data extraction, the codelists used and the column description.

## Citation information

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



## Table One
|                        |               | Missing   | Overall          | mortality (0)    | mortality (1)    |
|------------------------|---------------|-----------|------------------|------------------|------------------|
| **n**                  |               |           | 546906           | 508216           | 38690            |
| **sex, n (%)**         | F             | 0         | 278321 (50.9)    | 258683 (50.9)    | 19638 (50.8)     |
|                        | I             |           | 24 (0.0)         | 24 (0.0)         |                  |
|                        | M             |           | 268561 (49.1)    | 249509 (49.1)    | 19052 (49.2)     |
| **age, median [Q1,Q3]**|               | 0         | 32.5 [17.7,50.1] | 30.7 [16.2,45.5] | 73.5 [62.5,81.5] |
| **ethnicity, n (%)**   | BLACK         | 0         | 12714 (2.3)      | 12483 (2.5)      | 231 (0.6)        |
|                        | MISSING       |           | 157800 (28.9)    | 141135 (27.8)    | 16665 (43.1)     |
|                        | MIXED_RACE    |           | 6086 (1.1)       | 6012 (1.2)       | 74 (0.2)         |
|                        | OTHERS        |           | 8723 (1.6)       | 8626 (1.7)       | 97 (0.3)         |
|                        | SOUTH_ASIAN   |           | 32346 (5.9)      | 31912 (6.3)      | 434 (1.1)        |
|                        | WHITE         |           | 329237 (60.2)    | 308048 (60.6)    | 21189 (54.8)     |
| **country, n (%)**     | England       | 0         | 546906 (100.0)   | 508216 (100.0)   | 38690 (100.0)    |
| **health_auth, n (%)** | North East    | 0         | 38264 (7.0)      | 34315 (6.8)      | 3949 (10.2)      |
|                        | North West    |           | 175697 (32.1)    | 161074 (31.7)    | 14623 (37.8)     |
|                        | West Midlands |           | 87683 (16.0)     | 80784 (15.9)     | 6899 (17.8)      |
|                        | South West    |           | 96429 (17.6)     | 93063 (18.3)     | 3366 (8.7)       |
|                        | South Central |           | 118788 (21.7)    | 111428 (21.9)    | 7360 (19.0)      |
|                        | London        |           | 30045 (5.5)      | 27552 (5.4)      | 2493 (6.4)       |
| **mortality, n (%)**   | 0             | 0         | 508216 (92.9)    | 508216 (100.0)   |                  |
|                        | 1             |           | 38690 (7.1)      |                  | 38690 (100.0)    |
| **IMD, n (%)**         | 1.0           | 37354     | 85148 (16.7)     | 78691 (16.6)     | 6457 (17.9)      |
|                        | 2.0           |           | 118480 (23.3)    | 110284 (23.3)    | 8196 (22.7)      |
|                        | 3.0           |           | 80517 (15.8)     | 74875 (15.8)     | 5642 (15.6)      |
|                        | 4.0           |           | 113187 (22.2)    | 106223 (22.4)    | 6964 (19.3)      |
|                        | 5.0           |           | 112220 (22.0)    | 103372 (21.8)    | 8848 (24.5)      |

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

#### Baseline information

## License

## Publications
