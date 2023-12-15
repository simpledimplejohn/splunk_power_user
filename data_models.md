Data models

Objects:
- Events (index= host=)
- Searches (eval stats)
- Transactions   (like the transaction command, combinending multiple)

Fields: (Object Attributes)
- auto (made by splunk)
- lookup 
- eval (made in the eval expression)
- regex


BUILDING A DATA MODEL

Add Data
    Events (simplest)
    or 
    Search
Set fields
    lookup
    auto
    extract
    






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