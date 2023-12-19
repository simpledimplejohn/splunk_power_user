# calculated fiedls

will override an existing field with the same name unless you use 
coaless 
cannot chain calculate fields as the run in parallel 

props.conf
[source_type]
EVAL-<field_name> = <eval statment>

[access_logs]
EVAL-kilobytes = bytes/1024