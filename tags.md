# Tags

based on field values (as opposed to eventtypes which do this by search query)

Last thing to get assessed so that means you can tag an eventype 

How to search a tag (don't need index)
tag=successful_request
or
tag::status=successful_request

tag-successful_request

index=* status=*
| tags outputfield=all_tags  inclname=true inclvalue=true status

index=* "tag::status"=successful_request 
| tags outputfield=all_tags status

Computed last so it can also be
- calculate field
- event type
- lookup
- extrated field

tag.conf
[status=500]
FAILED = enabled

[status=503]
FAILED = enabled

[status=505]
FAILED = enabled