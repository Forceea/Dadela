# Identifiers

## Description

An identifier is a string that uniquely defines a component, e.g. a variable, list or template.

## Definitions

~~~
<VariableType> <Identifier>: <Expression>;
<VariableType> := { number | string | boolean | date }
~~~

## Notes

* An identifier starts with a letter and can contain letters (A..Z, a..z),
digits (0..9) and the underscore (_).
* An identifier is case-insensitive.

## Examples

~~~
number range: 100,                   	# variable
list MyList: (one, two, three)          # list
~~~