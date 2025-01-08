---
sidebar_position: 1
---

# Data Specification

## Best Practices for Sharing Water Level Data with the New Mexico Water Data Initiative
This document describes the New Mexico Water Data Initiative’s (WDI) preferred way to receive data related to measurements of the depth to water in groundwater wells.

This document outlines recommended best practices, not enforceable standards. It is understood that not all data providers will be able to report all of the information listed below, or in the exact format recommended.

Following the best practices listed below will allow water level measurement data to be more easily ingestible into the WDI tools. It will also increase consistency across the Water Data Catalog. In addition to this document, we have provided template files that can be used as examples.

If you have questions about this document, feel free to contact us at newmexicowaterdata@nmt.edu 

## File Structure and Format
### File Format
Water level  measurements should be provided in two separate files, one with location and well 
construction data, and one with water level measurements. The site_id field should be provided in both files to allow them to be joined. This reduces the amount of repeated information if there are many measurements for each well. It is preferred that all measurement data be provided in one measurement file even if there are multiple wells.

### File Type
The  preferred file type is Files should be provided as .csv tables. Excel spreadsheets with multiple 
tabs are not readable by the Data Catalog’s data API.

### File Names
The most important things to remember about file naming are to be consistent
and descriptive in naming your files so that it’s obvious what it contains. The preferred format for file names is as follows:

```
Agency_Location/Project/Report_DataType_YYYYMMDD_Version
```

the date could be a date range if data are collected over multiple years as in the example below.

```
NMBGMR_HealyNetwork_WL_2000_2024_v1
```


## Data Structure and Format
### Field Names
Recommended field names for both the location and measurement files are provided in the data 
dictionary tables below.  
- Field names (column headers) should be descriptive. 
- Field names should not include special characters except `_`.  
- Avoid using spaces and use underscores instead. 
- Do not begin field names with a number. 
- All field names should be in the first row. 
- Use all lowercase letters in field names.

### Formatting of Cells and Measurement Values
- List one value per cell. Do not put multiple observations, codes, types of data (e.g. date and time), coordinates, 
  etc. in one cell, dates (`YYYYMMDD`) do not need to be split out. 
- Do not merge cells. 
- Measurement values should be reported as depth to water  in feet below ground surface. 
- If continuous and manual measurements are included in the same table they should be in the same field and differentiated with a measurement_type field; time (`HH:MM AM/PM`); date (`YYYYMMDD`). 
- Do not include units in the same cells as values.

### Required and Desired Fields
The data dictionary tables below provide the minimum required fields and additional 
fields that increase the usefulness of the data. Required fields are necessary  for the data to be usable by WDI. 
Desired fields greatly increase the value and usability of the data provided. Data providers are welcome to provide 
additional fields to what are recommended here. **Locations without x,y data should not be included.**

### Units
Wherever a measurement value is provided, an additional field should be included specifying measurement 
units as shown in the data dictionaries below and in the example templates.
