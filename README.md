# KNIME quantity based averages
## aggregated weight-based year average features
by connecting two or more data tables features (i.e. quantities in good receipts) can be assigned to a meta data entity by matching keys. on base of every entry aggregated values for the features can be calculated. finally, for the meta data entity (weight-based) averages for specific time slots can be calculated
{workflow with test data (csv) // table export // no visualization)

## 01 data input
see the CSV files in the folder 01_input. For illustration 2 dummy files in CSV format were included.
#### Contract data
a row represents one contract for supplier/material/plant with a unique validity (valid from - valid to) and the corresponding price.
one material has a certain index (dummy refers to "100" as the base), so the Material Base is the Material Number without index.
#### GR data
The good receipts show one receipt per row, which refers to supplier/material/plant and a date of receipt. It contains the corresponding quantity of the material.

## 02 processing
the Contract data is splitted in several entries if the validation time period extends the turn of the year. Thus one row represents a validation of one year at a max, the year of "valid from" equals the year of "valid to".
the Contract data is extended with the quantity of materials, which arise in the validation timeframe.
The difference in price (active row to previous) is calculated.

## 03 results
#### Contract data as processed.
#### Contract data with quantity weighed price average per year
#### Contract data with quantity weighed price average per year for Material Base

## 50 importing the project
the full project is part of the KNAR-file and can be imported as it is in the KNIME analytics platform. 
The only workflow is called "WF" and can be imported separately. Choosing this option, the path to input data has to be reconfigured.

## 70 comments
the time series of contract data is quite often a challenge in data warehouses. The related quantities are located outside the data table and have to be attached. In many cases the calculation of a base price (year average with quantity weighting).
