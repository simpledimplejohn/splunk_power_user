# Splunk Power User Cert
This repo stores notes, commands, scripts, and resources for studying for the poweruser certification

## how to restart locally
`./bin/splunk stop`

## Data uploaded to splunk
Was unable to upload data until the server.conf file tag was added
[diskUsage]
minFreeSpace = 10


## Key topics to study for exam
- Data Models
    -- CIM
    - acceleration
    - pivots
-- Transaction Command
-- Work Flow Actions
- macros
-- Knolege Manager
-- Event types
- commands
     - fill null
     - chart
     - timechart
     - eval
     - search

## RE-LOADING SPLUNK
- stop splunk (somehow)
- drag it to the trash (save any apps you've made)
- go to splunk.com and download the trial again
- install 

## Jobs Inspector
- Header (events, scanned, time)
- Exicution Cost
- Properites (optimized search)

Events per second (EPS)
- number of events scanned/ time taken
Avtivities/Jobs 
- job manager 

## Trendline
- | trendline takes a rolling average
- sma5(value) simple moving average
- ema5(value) exponentaila moving averate
- wma5(value) weighted moving average
    - number is 2 - 100000
number is how many values it counts to calculate the average

index=* bytes=* 
| timechart span=1m sum(bytes) as bytes
| trendline sma100(bytes) as trend
| where bytes > trend

## eval case()
index=main status=*
| eval result = case(status == 200, "okay", status == 500, "bad")
| stats count by result

## eval tostring()
| makeresults
| eval now = 1703025610
| eval nowstring = tostring(now, "duration")
| table nowstring


## EXTRA NOTES

Operations
1. field extraction
2. field transform (field extraction with transform)
3. key-value field extraction KV_MODE?? (props.conf stanza)
4. field aliasing Fieldalias (props.conf)
5. calculated fields props.conf (EVAL)
6. lookup
7. Event type 
8. tag the last thing--so can not be conditional 

SEDCMD ananomyses data in the props.conf files, uses regex

FOLLOW UP ON 
- calcluated fields
- field extraction required ?
- tag searches are case senstive
- macros again
--- Which of the following can be used with the eval command tostring function? (Choose all that apply.)
    A. "hex"
    B. "commas"
    C. "decimal"
    D. "duration"
- data model acceleration
    B. Accelerated data models cannot be edited.
    C. Private data models cannot be accelerated.
    D. You must have administrative permissions or the accelerate_datamodel capability to accelerate a data model.
-- fillnull command with nothing sepcificed?  regurns 0?
--  Search workflow action,??
- D. tag::<field>=<tagname>
- It is no longer possible to edit the field extraction in the Field Extractor (FX) UI.

Data model fields can be added using the Auto-Extracted method.
Which of the following statements describe Auto-Extracted fields? (Choose all that apply.)
A. Auto-Extracted fields can be hidden in Pivot.
B. Auto-Extracted fields can have their data type changed.
C. Auto-Extracted fields can be given a friendly name for use in Pivot.
D. Auto-Extracted fields can be added if they already exist in the dataset with constraints.

