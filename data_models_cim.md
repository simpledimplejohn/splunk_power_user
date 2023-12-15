# CIM
common information model
download from splunk base
choose a preset based on your data type
(web)

has preset objects
-inherited
-extracted
-calculated fields

has a macro that searches your index/dataset

SETTING UP YOUR DATA MODEL
- Manage Apps
    - choose the data model 
    - add the index
- Go to the model 
    - only works with data taged with web
    - creating a pivot won't work 
- create an event type
    - tag the data to be in the model
    - make sure the tag is the correct one for the CIM
- create alieses for the fields 
    - field aliases 
    - use existing CIM fields 

Create a pivot and add to it

SEARCH THE MODEL WITH
| datamdel Web Web search

| datamodel Web Web search
| stats count by Web.src

