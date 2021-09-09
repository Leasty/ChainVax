# ChainVax


## Analyse Covid_Infeciton Rate ##

---

COVID19 data was collected from https://data.nsw.gov.au/nsw-covid-19-data.

Cleaned up data to remove null values and 'Masked' data.

Using pgeocode, iterate through the data frame index and collect longitutde and latitude values from the postcodes.

Prepare data frame by setting the date as the index, adding a count column and dropping unused columns.

Plot the data on a mapping of NSW using the longitutde and latitude data to show which areas are most affected by COIVD19.