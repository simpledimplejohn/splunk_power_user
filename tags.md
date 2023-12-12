# Tags

based on field values (as opposed to eventtypes which do this by search query)

How to search a tag (don't need index)
tag=successful_request
or
tag::status=successful_request

index=* status=*
| tags  includename=true includevalue=true status

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