# Pretty Printing with Python JSON Tool

JSON (JavaScript Object Notation) is a lightweight data-interchange format. 
It can be a collection of name/value pairs or an ordered list of values.

In Python 2.6+ you can use the built-in json tool to validate and pretty-print.

```bash
$ cat foo
{"one":1,"two":2,"three":3,"four":4,"five":5}
```
Use Python's JSON tool to pretty-print the output:

```bash
$ cat foo | python -m json.tool
{
    "one": 1,
    "two": 2,
    "three": 3,
    "four": 4,
    "five": 5  
}
```
JSON output can be difficult to read due to length or complexity (logs), this
tool will assist with parsing and beautifying the output.
