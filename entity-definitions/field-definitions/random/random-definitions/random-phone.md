# Random phone numbers

## Description

Generates random phone numbers.

## Definitions

~~~
random type(phone) format(<FormatString>)
~~~

## Notes

The format string defines the structure of the phone numbers, using some special characters:
* D: a digit from 0 to 9.
* d: a digit from 1 to 9.

Dadela will not raise an error if illegal characters are used in the format string, e.g. 210xD-00-DDD.

## Examples

~~~
random type(phone) format("(30) 210 dD-00-DD")
~~~