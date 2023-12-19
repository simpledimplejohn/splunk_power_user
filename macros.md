MACRO's
reusable portion of a search
name and definition are the only required 

what is the eval macro vs not?
expecting a string
non eval
add the search string

NAME must include arguments if there are any
DEFINITION uses $$ to declare the search string
ARGUMENTS the field names being used

`eval total = $money$ * ($money$ * $perc$)/100` not an eval macro 




If you re-use a search use macros
then if you need to change the search you only need to do it in one place

settings/advanced search



macros.conf file

can be searched with a pipe or used on their own
to search the macro:
| `macro_here(arguments,here)`


command shift E will show the macro search

you can use
tags
event types
