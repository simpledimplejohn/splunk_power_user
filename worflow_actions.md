WORKFLOW ACTIONS:

found in the fields menue

- Build event type
- Extract Fields 
- Show source 

GET
SEARCH
POST no authentication

settings/fields/workflowactions
new

Once new created fill out the following
- name (unique)
- Label (will show under the event action menue) you can add a token "$field_to_run_action_on$"
- Apply only to the following fields (* or list of field names)
- Apply to the event types: 
- Show action in (Event menu, Field menu, Both)
- Action type (link or secondary search)
- URI (the endpoint ) www.google.com/search?q=$field_to_search$
- link method (GET vs POST) 

SET PERMISSIONS

SEARCH:
runs a secondary search
tokenized
enter a time range when the action is built
    or use the time range that was run in the search

GET
opens a link based on the fields
only used to request data
is visable in the url
could be used to post to a dashboard

POST
url to post to 
arguments (key value pairs to post)
not visable in the URL

USING A CONF FILES
workflow_actions.conf store
default
$SPLUNK_HOME/etc/apps/search/default/ for reference.

[show_source]
type=link 
label = Show Source


Actions:
GET
POST
search
