## Event Types
Is a saved search string that when it shows up will show a color
and if its called it will run the query


Catagorize data KO
Based on query string (as oposed to tags based on field value)
Assigned on search time
Multi Valu Field
Cost in Search Performance




Event types must follow this 
cannot ref tags
cannot include pipe
cannot include subsearch

Has
- Name
- Tags
- Color
- Priority

Specific events--higher priority
broad events -- lower priority

eventypes.conf  splunk/etc/apps/appname/local/eventypes.conf
[Successful Purchase]
color = et_green
priority = 5
search = index="testsenstive" sourcetype=access_combined_wcookie  status=200 action=purchase

[success_event]
color = et_blue
priority = 6
search = index="testsenstive" sourcetype=access_combined_wcookie  status=200

[action-%action%]
color = et_orange 
priority = 1
search = index="testsenstive" sourcetype=access_combined_wcookie  

## Searches
eventtype = success_event

index="testsenstive" sourcetype=access_combined_wcookie  
| findtypes max=20