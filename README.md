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

#### Patient demographics

## License

## Publications
