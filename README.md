# OPTIMAL master dataset documentation
### Version: 0.1


DExtER prints one line per patient for new data extractions, for any additional baseline/outcome variables and time-series data. Many of the data fields printed carry a prefix (and sometimes a suffix as well) to help users easily identify what type of variables they are. Sections below provide a detailed overview of the methodology used for data extraction, the codelists used and the column description.

## Citation information

## Methodology

### Codelist

## Database Sources and Linkage
#### Database
| Name      | Build version | Last collection date |
|:----------|--------------:|---------------------:|
|CPRD AURUM | May, 2022     | 31st April, 2022     |

#### Linked database
| Name    | Linked to  | Build date  |
|:--------|-----------:|------------:|
|IMD data | CPRD AURUM |             |


## File Structure

## Outputs

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
