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
|IMD                 | Indices of multiple deprivation  (essentially a measure of poverty).                                      | Categorical|

#### Baseline information
| Column name        | Description                                                                                               | Data type  |
|:-------------------|:----------------------------------------------------------------------------------------------------------|:-----------|
| B_MEDI:HF_BHAM_CAM_FINAL:0                           | column for **hf** if diagnosed and records the codes                                        | Numeric    |
| BD_MEDI:HF_BHAM_CAM_FINAL:0                          | date column for **hf** to record when the diagnosed was made.                               | Date       |
| B_MEDI:AF_BHAM_CAM:1                                 | column for **af** if diagnosed and records the codes                                        | Numeric    |
| BD_MEDI:AF_BHAM_CAM:1                                | date column for **af** to record when the diagnosed was made.                               | Date       |
| B_MEDI:ISCHAEMICSTROKE_BHAM_CAM:2                    | column for **ischaemicstroke** if diagnosed and records the codes                           | Numeric    |
| BD_MEDI:ISCHAEMICSTROKE_BHAM_CAM:2                   | date column for **ischaemicstroke** to record when the diagnosed was made.                  | Date       |
| B_MEDI:STROKEUNSPECIFIED_BHAM_CAM:3                  | column for **strokeunspecified** if diagnosed and records the codes                         | Numeric    |
| BD_MEDI:STROKEUNSPECIFIED_BHAM_CAM:3                 | date column for **strokeunspecified** to record when the diagnosed was made.                | Date       |
| B_MEDI:STROKE_HAEMRGIC_BHAM_CAM:4                    | column for **stroke haemrgic** if diagnosed and records the codes                           | Numeric    |
| BD_MEDI:STROKE_HAEMRGIC_BHAM_CAM:4                   | date column for **stroke haemrgic** to record when the diagnosed was made.                  | Date       |
| B_MEDI:HYPERTENSION_BHAM_CAM:5                       | column for **hypertension** if diagnosed and records the codes                              | Numeric    |
| BD_MEDI:HYPERTENSION_BHAM_CAM:5                      | date column for **hypertension** to record when the diagnosed was made.                     | Date       |
| B_MEDI:MINFARCTION_BHAM_CAM:6                        | column for **minfarction** if diagnosed and records the codes                               | Numeric    |
| BD_MEDI:MINFARCTION_BHAM_CAM:6                       | date column for **minfarction** to record when the diagnosed was made.                      | Date       |
| B_MEDI:IHD_NOMI_BHAM_CAM:7                           | column for **ihd nomi** if diagnosed and records the codes                                  | Numeric    |
| BD_MEDI:IHD_NOMI_BHAM_CAM:7                          | date column for **ihd nomi** to record when the diagnosed was made.                         | Date       |
| B_MEDI:PAD_STRICT_BHAM_CAM:8                         | column for **pad strict** if diagnosed and records the codes                                | Numeric    |
| BD_MEDI:PAD_STRICT_BHAM_CAM:8                        | date column for **pad strict** to record when the diagnosed was made.                       | Date       |
| B_MEDI:VALVULARDISEASES_BHAM_CAM:9                   | column for **valvulardiseases** if diagnosed and records the codes                          | Numeric    |
| BD_MEDI:VALVULARDISEASES_BHAM_CAM:9                  | date column for **valvulardiseases** to record when the diagnosed was made.                 | Date       |
| B_MEDI:AORTICANEURYSM_BHAM_CAM:10                    | column for **aorticaneurysm** if diagnosed and records the codes                            | Numeric    |
| BD_MEDI:AORTICANEURYSM_BHAM_CAM:10                   | date column for **aorticaneurysm** to record when the diagnosed was made.                   | Date       |
| B_MEDI:TYPE1DM_11_3_21_BIRM_CAM:11                   | column for **type1dm** if diagnosed and records the codes                                   | Numeric    |
| BD_MEDI:TYPE1DM_11_3_21_BIRM_CAM:11                  | date column for **type1dm** to record when the diagnosed was made.                          | Date       |
| B_MEDI:TYPE2DIABETES_11_3_21_BIRM_CAM:12             | column for **type2diabetes** if diagnosed and records the codes                             | Numeric    |
| BD_MEDI:TYPE2DIABETES_11_3_21_BIRM_CAM:12            | date column for **type2diabetes** to record when the diagnosed was made.                    | Date       |
| B_MEDI:CKDSTAGE3TO5_BHAM_CAM:13                      | column for **ckdstage3to5** if diagnosed and records the codes                              | Numeric    |
| BD_MEDI:CKDSTAGE3TO5_BHAM_CAM:13                     | date column for **ckdstage3to5** to record when the diagnosed was made.                     | Date       |
| B_MEDI:DEPRESSION_BIRM_CAM:14                        | column for **depression** if diagnosed and records the codes                                | Numeric    |
| BD_MEDI:DEPRESSION_BIRM_CAM:14                       | date column for **depression** to record when the diagnosed was made.                       | Date       |
| B_MEDI:ANXIETY_BIRM_CAM:15                           | column for **anxiety** if diagnosed and records the codes                                   | Numeric    |
| BD_MEDI:ANXIETY_BIRM_CAM:15                          | date column for **anxiety** to record when the diagnosed was made.                          | Date       |
| B_MEDI:BIPOLAR_BIRM_CAM:16                           | column for **bipolar** if diagnosed and records the codes                                   | Numeric    |
| BD_MEDI:BIPOLAR_BIRM_CAM:16                          | date column for **bipolar** to record when the diagnosed was made.                          | Date       |
| B_MEDI:EATINGDISORDERS_BIRM_CAM:17                   | column for **eatingdisorders** if diagnosed and records the codes                           | Numeric    |
| BD_MEDI:EATINGDISORDERS_BIRM_CAM:17                  | date column for **eatingdisorders** to record when the diagnosed was made.                  | Date       |
| B_MEDI:SCHIZOPHRENIAMM:18                            | column for **schizophreniamm** if diagnosed and records the codes                           | Numeric    |
| BD_MEDI:SCHIZOPHRENIAMM:18                           | date column for **schizophreniamm** to record when the diagnosed was made.                  | Date       |
| B_MEDI:PTSD_TLC_V2:19                                | column for **ptsd** if diagnosed and records the codes                                      | Numeric    |
| BD_MEDI:PTSD_TLC_V2:19                               | date column for **ptsd** to record when the diagnosed was made.                             | Date       |
| B_MEDI:AUTISM_BIRM_CAM:20                            | column for **autism** if diagnosed and records the codes                                    | Numeric    |
| BD_MEDI:AUTISM_BIRM_CAM:20                           | date column for **autism** to record when the diagnosed was made.                           | Date       |
| B_MEDI:ALCOHOLMISUSE_BIRM_CAM:21                     | column for **alcoholmisuse** if diagnosed and records the codes                             | Numeric    |
| BD_MEDI:ALCOHOLMISUSE_BIRM_CAM:21                    | date column for **alcoholmisuse** to record when the diagnosed was made.                    | Date       |
| B_MEDI:SUBSTANCEMISUSE_BIRM_CAM:22                   | column for **substancemisuse** if diagnosed and records the codes                           | Numeric    |
| BD_MEDI:SUBSTANCEMISUSE_BIRM_CAM:22                  | date column for **substancemisuse** to record when the diagnosed was made.                  | Date       |
| B_MEDI:CHRONIC_LIVER_DISEASE_ALCOHOL_BIRM_CAM:23     | column for **chronic liver disease alcohol** if diagnosed and records the codes             | Numeric    |
| BD_MEDI:CHRONIC_LIVER_DISEASE_ALCOHOL_BIRM_CAM:23    | date column for **chronic liver disease alcohol** to record when the diagnosed was made.    | Date       |
| B_MEDI:NAFLD_BIRM_CAM:24                             | column for **nafld** if diagnosed and records the codes                                     | Numeric    |
| BD_MEDI:NAFLD_BIRM_CAM:24                            | date column for **nafld** to record when the diagnosed was made.                            | Date       |
| B_MEDI:OTHER_CHRONIC_LIVER_DISEASE_OPTIMAL:25        | column for **other chronic liver disease** if diagnosed and records the codes               | Numeric    |
| BD_MEDI:OTHER_CHRONIC_LIVER_DISEASE_OPTIMAL:25       | date column for **other chronic liver disease** to record when the diagnosed was made.      | Date       |
| B_MEDI:ULCERATIVE_COLITIS_BIRM_CAM:26                | column for **ulcerative colitis** if diagnosed and records the codes                        | Numeric    |
| BD_MEDI:ULCERATIVE_COLITIS_BIRM_CAM:26               | date column for **ulcerative colitis** to record when the diagnosed was made.               | Date       |
| B_MEDI:CROHNS_DISEASE_BIRM_CAM:27                    | column for **crohns disease** if diagnosed and records the codes                            | Numeric    |
| BD_MEDI:CROHNS_DISEASE_BIRM_CAM:27                   | date column for **crohns disease** to record when the diagnosed was made.                   | Date       |
| B_MEDI:PREVALENT_IBS_BIRM_CAM:28                     | column for **prevalent ibs** if diagnosed and records the codes                             | Numeric    |
| BD_MEDI:PREVALENT_IBS_BIRM_CAM:28                    | date column for **prevalent ibs** to record when the diagnosed was made.                    | Date       |
| B_MEDI:ALL_DEMENTIA_BIRM_CAM:29                      | column for **all dementia** if diagnosed and records the codes                              | Numeric    |
| BD_MEDI:ALL_DEMENTIA_BIRM_CAM:29                     | date column for **all dementia** to record when the diagnosed was made.                     | Date       |
| B_MEDI:PARKINSONS_BIRM_CAM:30                        | column for **parkinsons** if diagnosed and records the codes                                | Numeric    |
| BD_MEDI:PARKINSONS_BIRM_CAM:30                       | date column for **parkinsons** to record when the diagnosed was made.                       | Date       |
| B_MEDI:EPILEPSY_BIRM_CAM:31                          | column for **epilepsy** if diagnosed and records the codes                                  | Numeric    |
| BD_MEDI:EPILEPSY_BIRM_CAM:31                         | date column for **epilepsy** to record when the diagnosed was made.                         | Date       |
| B_MEDI:ALLCA_NOBCC_VFINAL_BIRM_CAM:32                | column for **allca nobcc** if diagnosed and records the codes                               | Numeric    |
| BD_MEDI:ALLCA_NOBCC_VFINAL_BIRM_CAM:32               | date column for **allca nobcc** to record when the diagnosed was made.                      | Date       |
| B_MEDI:LYMPHOMA_PREVALENCE_BIRM_CAM:33               | column for **lymphoma prevalence** if diagnosed and records the codes                       | Numeric    |
| BD_MEDI:LYMPHOMA_PREVALENCE_BIRM_CAM:33              | date column for **lymphoma prevalence** to record when the diagnosed was made.              | Date       |
| B_MEDI:LEUKAEMIA_PREVALENCE_BIRM_CAM:34              | column for **leukaemia prevalence** if diagnosed and records the codes                      | Numeric    |
| BD_MEDI:LEUKAEMIA_PREVALENCE_BIRM_CAM:34             | date column for **leukaemia prevalence** to record when the diagnosed was made.             | Date       |
| B_MEDI:PLASMACELL_NEOPLASM_BIRM_CAM:35               | column for **plasmacell neoplasm** if diagnosed and records the codes                       | Numeric    |
| BD_MEDI:PLASMACELL_NEOPLASM_BIRM_CAM:35              | date column for **plasmacell neoplasm** to record when the diagnosed was made.              | Date       |
| B_MEDI:ASTHMA_PUSHASTHMA:36                          | column for **asthma pushasthma** if diagnosed and records the codes                         | Numeric    |
| BD_MEDI:ASTHMA_PUSHASTHMA:36                         | date column for **asthma pushasthma** to record when the diagnosed was made.                | Date       |
| B_MEDI:COPD_BIRM_CAM:37                              | column for **copd** if diagnosed and records the codes                                      | Numeric    |
| BD_MEDI:COPD_BIRM_CAM:37                             | date column for **copd** to record when the diagnosed was made.                             | Date       |
| B_MEDI:OSA_BIRM_CAM:38                               | column for **osa** if diagnosed and records the codes                                       | Numeric    |
| BD_MEDI:OSA_BIRM_CAM:38                              | date column for **osa** to record when the diagnosed was made.                              | Date       |
| B_MEDI:BRONCHIECTASIS_BIRM_CAM:39                    | column for **bronchiectasis** if diagnosed and records the codes                            | Numeric    |
| BD_MEDI:BRONCHIECTASIS_BIRM_CAM:39                   | date column for **bronchiectasis** to record when the diagnosed was made.                   | Date       |
| B_MEDI:CYSTICFIBROSIS_BIRM_CAM:40                    | column for **cysticfibrosis** if diagnosed and records the codes                            | Numeric    |
| BD_MEDI:CYSTICFIBROSIS_BIRM_CAM:40                   | date column for **cysticfibrosis** to record when the diagnosed was made.                   | Date       |
| B_MEDI:ATOPICECZEMA_BIRM_CAM:41                      | column for **atopiceczema** if diagnosed and records the codes                              | Numeric    |
| BD_MEDI:ATOPICECZEMA_BIRM_CAM:41                     | date column for **atopiceczema** to record when the diagnosed was made.                     | Date       |
| B_MEDI:ALLERGICRHINITISCONJ_BIRM_CAM:42              | column for **allergicrhinitisconj** if diagnosed and records the codes                      | Numeric    |
| BD_MEDI:ALLERGICRHINITISCONJ_BIRM_CAM:42             | date column for **allergicrhinitisconj** to record when the diagnosed was made.             | Date       |
| B_MEDI:HIVAIDS_BIRM_CAM:43                           | column for **hivaids** if diagnosed and records the codes                                   | Numeric    |
| BD_MEDI:HIVAIDS_BIRM_CAM:43                          | date column for **hivaids** to record when the diagnosed was made.                          | Date       |
| B_MEDI:OSTEOPOROSIS_BIRM_CAM:44                      | column for **osteoporosis** if diagnosed and records the codes                              | Numeric    |
| BD_MEDI:OSTEOPOROSIS_BIRM_CAM:44                     | date column for **osteoporosis** to record when the diagnosed was made.                     | Date       |
| B_MEDI:OSTEOARTHRITIS_MM_BIRM_CAM:45                 | column for **osteoarthritis** if diagnosed and records the codes                            | Numeric    |
| BD_MEDI:OSTEOARTHRITIS_MM_BIRM_CAM:45                | date column for **osteoarthritis** to record when the diagnosed was made.                   | Date       |
| B_MEDI:RHEUMATOIDARTHRITIS_MM_BIRM_CAM:46            | column for **rheumatoidarthritis** if diagnosed and records the codes                       | Numeric    |
| BD_MEDI:RHEUMATOIDARTHRITIS_MM_BIRM_CAM:46           | date column for **rheumatoidarthritis** to record when the diagnosed was made.              | Date       |
| B_MEDI:GOUT_MM_BIRM_CAM:47                           | column for **gout** if diagnosed and records the codes                                      | Numeric    |
| BD_MEDI:GOUT_MM_BIRM_CAM:47                          | date column for **gout** to record when the diagnosed was made.                             | Date       |
| B_MEDI:SYSTEMIC_LUPUS_ERYTHEMATOSUS_MM_BIRM_CAM:48   | column for **systemic lupus erythematosus** if diagnosed and records the codes              | Numeric    |
| BD_MEDI:SYSTEMIC_LUPUS_ERYTHEMATOSUS_MM_BIRM_CAM:48  | date column for **systemic lupus erythematosus** to record when the diagnosed was made.     | Date       |
| B_MEDI:SJOGRENSSYNDROME_BHAM_CAM:49                  | column for **sjogrenssyndrome** if diagnosed and records the codes                          | Numeric    |
| BD_MEDI:SJOGRENSSYNDROME_BHAM_CAM:49                 | date column for **sjogrenssyndrome** to record when the diagnosed was made.                 | Date       |
| B_MEDI:SYSTEMIC_SCLEROSIS_MM_BIRM_CAM:50             | column for **systemic sclerosis** if diagnosed and records the codes                        | Numeric    |
| BD_MEDI:SYSTEMIC_SCLEROSIS_MM_BIRM_CAM:50            | date column for **systemic sclerosis** to record when the diagnosed was made.               | Date       |
| B_MEDI:PMRANDGCA_MM_BIRM_CAM:51                      | column for **pmrandgca** if diagnosed and records the codes                                 | Numeric    |
| BD_MEDI:PMRANDGCA_MM_BIRM_CAM:51                     | date column for **pmrandgca** to record when the diagnosed was made.                        | Date       |
| B_MEDI:CHRONICFATIGUESYNDROMEMM_BIRM_CAM:52          | column for **chronicfatiguesyndromemm** if diagnosed and records the codes                  | Numeric    |
| BD_MEDI:CHRONICFATIGUESYNDROMEMM_BIRM_CAM:52         | date column for **chronicfatiguesyndromemm** to record when the diagnosed was made.         | Date       |
| B_MEDI:FIBROMYALGIA_BHAM_CAM:53                      | column for **fibromyalgia** if diagnosed and records the codes                              | Numeric    |
| BD_MEDI:FIBROMYALGIA_BHAM_CAM:53                     | date column for **fibromyalgia** to record when the diagnosed was made.                     | Date       |
| B_MEDI:POLYCYSTIC_OVARIAN_SYNDROME_PCOS_BIRM_CAM:54  | column for **polycystic ovarian syndrome pcos** if diagnosed and records the codes          | Numeric    |
| BD_MEDI:POLYCYSTIC_OVARIAN_SYNDROME_PCOS_BIRM_CAM:54 | date column for **polycystic ovarian syndrome pcos** to record when the diagnosed was made. | Date       |
| B_MEDI:ENDOMETRIOSIS_ADENOMYOSIS_BIRM_CAM:55         | column for **endometriosis adenomyosis** if diagnosed and records the codes                 | Numeric    |
| BD_MEDI:ENDOMETRIOSIS_ADENOMYOSIS_BIRM_CAM:55        | date column for **endometriosis adenomyosis** to record when the diagnosed was made.        | Date       |
| B_MEDI:HYPOTHYROIDISM_DRAFT_V1_BIRM_CAM:56           | column for **hypothyroidism** if diagnosed and records the codes                            | Numeric    |
| BD_MEDI:HYPOTHYROIDISM_DRAFT_V1_BIRM_CAM:56          | date column for **hypothyroidism** to record when the diagnosed was made.                   | Date       |
| B_MEDI:HYPERTHYROIDISM_V2_BIRM_CAM:57                | column for **hyperthyroidism** if diagnosed and records the codes                           | Numeric    |
| BD_MEDI:HYPERTHYROIDISM_V2_BIRM_CAM:57               | date column for **hyperthyroidism** to record when the diagnosed was made.                  | Date       |
| B_MEDI:ADDISON_DISEASE_BIRM_CAM:58                   | column for **addison disease** if diagnosed and records the codes                           | Numeric    |
| BD_MEDI:ADDISON_DISEASE_BIRM_CAM:58                  | date column for **addison disease** to record when the diagnosed was made.                  | Date       |
| B_MEDI:MS_120421_BIRM_CAM:59                         | column for **ms** if diagnosed and records the codes                                        | Numeric    |
| BD_MEDI:MS_120421_BIRM_CAM:59                        | date column for **ms** to record when the diagnosed was made.                               | Date       |
| B_MEDI:VISUAL_IMPAIRMENT_BIRM_CAM:60                 | column for **visual impairment** if diagnosed and records the codes                         | Numeric    |
| BD_MEDI:VISUAL_IMPAIRMENT_BIRM_CAM:60                | date column for **visual impairment** to record when the diagnosed was made.                | Date       |
| B_MEDI:ANY_DEAFNESS_HEARING_LOSS_BIRM_CAM:61         | column for **any deafness hearing loss** if diagnosed and records the codes                 | Numeric    |
| BD_MEDI:ANY_DEAFNESS_HEARING_LOSS_BIRM_CAM:61        | date column for **any deafness hearing loss** to record when the diagnosed was made.        | Date       |
| B_MEDI:MENIERESDISEASE_BIRM_CAM:62                   | column for **menieresdisease** if diagnosed and records the codes                           | Numeric    |
| BD_MEDI:MENIERESDISEASE_BIRM_CAM:62                  | date column for **menieresdisease** to record when the diagnosed was made.                  | Date       |
| B_MEDI:PERIPHERAL_NEUROPATHY_BIRM_CAM:63             | column for **peripheral neuropathy** if diagnosed and records the codes                     | Numeric    |
| BD_MEDI:PERIPHERAL_NEUROPATHY_BIRM_CAM:63            | date column for **peripheral neuropathy** to record when the diagnosed was made.            | Date       |
| B_MEDI:LEARNINGDISABILITY_BIRM_CAM:64                | column for **learningdisability** if diagnosed and records the codes                        | Numeric    |
| BD_MEDI:LEARNINGDISABILITY_BIRM_CAM:64               | date column for **learningdisability** to record when the diagnosed was made.               | Date       |
| B_MEDI:DOWNSSYNDROME_BIRM_CAM:65                     | column for **downssyndrome** if diagnosed and records the codes                             | Numeric    |
| BD_MEDI:DOWNSSYNDROME_BIRM_CAM:65                    | date column for **downssyndrome** to record when the diagnosed was made.                    | Date       |
| B_MEDI:PERNICIOUSANAEMIA_BIRM_CAM:66                 | column for **perniciousanaemia** if diagnosed and records the codes                         | Numeric    |
| BD_MEDI:PERNICIOUSANAEMIA_BIRM_CAM:66                | date column for **perniciousanaemia** to record when the diagnosed was made.                | Date       |
| B_MEDI:SICKLE_CELL_DISEASE_BIRM_CAM:67               | column for **sickle cell disease** if diagnosed and records the codes                       | Numeric    |
| BD_MEDI:SICKLE_CELL_DISEASE_BIRM_CAM:67              | date column for **sickle cell disease** to record when the diagnosed was made.              | Date       |
| B_MEDI:PSORIASIS_BIRM_CAM:68                         | column for **psoriasis** if diagnosed and records the codes                                 | Numeric    |
| BD_MEDI:PSORIASIS_BIRM_CAM:68                        | date column for **psoriasis** to record when the diagnosed was made.                        | Date       |
| B_MEDI:PSORIATICARTHRITIS2021_MM_BIRM_CAM:69         | column for **psoriaticarthritis** if diagnosed and records the codes                        | Numeric    |
| BD_MEDI:PSORIATICARTHRITIS2021_MM_BIRM_CAM:69        | date column for **psoriaticarthritis** to record when the diagnosed was made.               | Date       |
| B_MEDI:ILD_SH_20092020_BIRM_CAM:70                   | column for **ild sh** if diagnosed and records the codes                                    | Numeric    |
| BD_MEDI:ILD_SH_20092020_BIRM_CAM:70                  | date column for **ild sh** to record when the diagnosed was made.                           | Date       |
| B_MEDI:HAEMOCHROMATOSIS_BIRM_CAM:71                  | column for **haemochromatosis** if diagnosed and records the codes                          | Numeric    |
| BD_MEDI:HAEMOCHROMATOSIS_BIRM_CAM:71                 | date column for **haemochromatosis** to record when the diagnosed was made.                 | Date       |
## License

## Publications
