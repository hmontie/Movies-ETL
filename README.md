# Movies-ETL

## Project Overview

In this module, you’ll learn how to use the Extract, Transform, Load (ETL) process to create data pipelines. A data pipeline moves data from a source to a destination, and the ETL process creates data pipelines that also transform the data along the way. Analysis is impossible without access to good data, so creating data pipelines is often the first step before any analysis can be performed. Therefore, understanding ETL is an essential skill for data analysis.

## Challenge Overview

1. In order to build a function and automate the ETL process for the challenge, we made the following assumptions:

 - The updated data will stay in the same formats:

2. We're creating a function that will extract, transform and load updated csv files if, and only if, the new data is in the same format as the intial datasets. We know that there is a possibility for the data structure to change overtime and early data inspection of new files will be crucial.
There is competing data between the different datasets. Based on observed patterns, we have built a system to transform for the best possible outcome:

  - We're assuming that the future datasets will follow the same pattern as the initialone.

3. We're dropping rows with corrupted data when two movies got merged based on release date filtering:

  -We're assuming that the time range we have selected based on our intial dataser will help us catch and drop outliers from dataset, without deleting good data.
We're dropping columns with only one value:

4. We're dropping columns with only one value: 
 
 -We added an exception to print "No columns to drop because of only one value" if this happens with the new dataset. We want the function to keep running withour errors.

5. New updated files will be included in the section "Declaring new files to upload":

  -To allow the function to run properly, files have to be inputted in the right place.

## Challenge Summary
### Documented Assumptions:

The data provided will always be in the correct file format like .json or .csv. If the data provided is not in that format the ETL pipeline will break. The spelling of columns names will remain consistent. Columns will not be removed from the datasets. The formatting of dollar amounts, dates, times, or other numbers will not change as this could break our regex expressions. The sql database tables will not be dropped by anyone else and the data will always be deleted and replaced instead of appended to exisiting data. Things like removing adult movies, not including TV shows, and removing rows based on conditions are all built into the function specifically so they can't change their mind later without refactoring the function.
