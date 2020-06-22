# Variables

## Description

A variable is a data storage.

## Definitions

~~~
<VariableType> <Identifier>: <Expression>

<VariableType> := { number | string | boolean | date }
~~~

## Notes

* The main usage of variables is to assign the same value to different components.
* The `number` variable includes the arithmetic expressions found in most programming languages (see examples).
* The `string` variable uses <space> as a concatenator (see examples).
The double quotations are used when a string includes a <space>, a comma (,) or a variable reference (@var).
* A variable is called using `@<VariableIdentifier>`, e.g `@myVar`.
* The suggested capitalization is camelCase, e.g. `myVar`.

## Examples

~~~
# Integer
number range: 100,													# result: "100"
number start: 1,													# result: "1"
number end: @start + @range,										# result: "101"
number a: 2 * (@range - @start) / 1.5,								# result: "132"

# String
string myDate1: Monday,                                            	# result: "Monday"
string myDate2: Today is Monday,                                 	# result: "Today is Monday"
string myDate3: "Monday is the " @start "st day of the week",      	# result: "Monday is the 1st day of the week"
string myDate4: Monday is not@start but @start st,                 	# result: "Monday is not@start but 1st"
string myDate5: "Monday is @start " @start " day",                 	# result: "Monday is @start 1 day"

# Boolean
boolean isUrgent: true,                 							# result: "true"
boolean isUrgent: @range > 1,           							# result: "true"
boolean isUrgent: @range: 99,										# result: "false"

# Date
date date1: 2018-01-01 15:22:00,
date date2: 2018-12-31,
~~~
