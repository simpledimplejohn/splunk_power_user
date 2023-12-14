WORKFLOW ACTIONS:

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
