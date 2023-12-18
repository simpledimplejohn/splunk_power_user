These are a knolege object

Objects:
- Events (index= host=)
- Searches (eval stats)
- Transactions   (like the transaction command, combinending multiple)

Fields: (Object Attributes) auto-extracted, eval expression, regular expression
- auto (made by splunk)
- lookup 
- eval (made in the eval expression)
- regex
- geo location 


BUILDING A DATA MODEL

Add Data
    Events (simplest)
    or 
    Search  
Set fields
    lookup
    auto
    extract   The fields can include calculated fields, user-defined field extractions, and fields added to your data by lookups.

DataSets
Event datasets, search datasets, transaction datasets, and child datasets.
The top-level event, search, and transaction datasets in data models are collectively referred to as "root datasets."

CONSTRAINTS-- this is just another word for the search query
- transaction constriants means using the transaction command

ACCELERATION:
-must have a root dataset
- and a streaming command

    






How to create/write data models in Splunk
https://www.youtube.com/watch?v=N3FL6rawDLQ&list=PLSr58-DJdRybowRyR8gp4cbLtoQektcze

Records 1 root data sets
Event data sets (no piepline search, only condition)
Root data sets (give complex search or transforming comand)
Transaction data set 

```Constraints ```
index="zomato" "Country Code"="*" "Country Code"!=1


```Base search```
index="zomato" "Country Code"="*" "Country Code"!=1
| lookup countries.csv country-code as "Country Code" output name as name region as region sub-region as sub-region
| stats count by "Country Code" name region sub-region

```ADUJSTED FOR FIELD NAME```
index="zomato" "Country Code"="*" "Country Code"!=1
| eval country_code = 'Country Code'
| lookup countries.csv country-code as country_code output name as name region as region sub-region as sub-region
| stats count by "Country Code" name region sub-region country_code

```ADDINGING LOOKUP ```
field in lookup = field in dataset 

Then add a pivot to do the query and create the visualization