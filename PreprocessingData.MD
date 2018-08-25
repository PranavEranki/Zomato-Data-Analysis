An explanation of all of the steps taken in the file
PreprocessingData.py

## Steps:
1. Imports
2. Identification of columns
3. Removing nan, null values
4. Explored the column 'Country Code' for a bit
5. Created a list of columns we need
6. Skipped unneeded columns : 
    * 'Restaurant Name'
    * 'Restaurant ID'
    * 'City'
    * 'Address'
7. Explored columns, then ignored :
    * 'Locality'
    * 'Locality Verbose'
    * 'Longitude'
    * 'Latitude'
8. Found cuisines. Explored this column for a while, as it seemed quite important.
9. Explored both columns 'Currency' and 'Average Cost for two':
    * Here, I first viewed both columns
    * Then, I checked for any non-rupee columns
    * Then, I removed all non-rupee columns
    * This essentially isolated data to only containing rupees (Indian currency)
10. Viewed Value counts for some other columns:
    * 'Has Table booking'
    * 'Has Online delivery'
    * 'Is delivering now'
    * 'Switch to order menu'
    * 'Price Range'
11. Added some more columns to wanted:
    * 'Has Table booking'
    * 'Has Online delivery'
    * 'Price range'
12. Examined some possible Y values in any ML related problem
    * 'Aggregate rating'
    * 'Rating color'
    * 'Rating text'
    * 'Votes'
13. Added the value 'Aggregate rating' as it seemed the most intuitive, useful column
14. Now, I processed the cuisines column:
    * Ran through entire column
    * Changed value for each element in each column to the number of cuisines offered
15. Lastly, I processed the rating column:
    * Ran through entire column
    * Removed values which said rating of 0 - probably trolling or mislabeled data
15. Got the data which I wanted out of the main data
16. Saved the data, called 'Cleaned Data', to a file called 'CleanedData.csv'