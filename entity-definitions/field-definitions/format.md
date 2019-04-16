# Format parameter

## Description

Defines the format of a number (integer or decimal).

## Definitions

~~~
format(<FormatString>)
~~~

## Notes

* For the application of this parameter, see the examples.

## Examples

~~~
number = 12.34

format(0)           result: "12"
format(00)          result: "12"
format(p00)         result: "p12"

format(0.0)         result: "12.3"
format(0.00)        result: "12.34"
format(0.000)       result: "12.340"
format(0.0abc)      result: "12.34bc"

format(00.0)        result: "12.3"
format(00.00)       result: "12.34"
format(00.000)      result: "12.340"

format(xxx.0)       result: "x12.3"
format(yyy.00)      result: "y12.34"
format(zzz.00x)     result: "z12.34x"

format(.00)         result: ERROR
format(0.)          result: ERROR
~~~