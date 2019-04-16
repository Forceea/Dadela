# Static

## Description

Generates data with a literal value.

## Definitions

~~~
static value( { <String | Variable> } ) [ format<FormatString>) ]
~~~

## Notes

* If the type of <Variable> is `number`, the (optional) `format` parameter can be used.

## Examples

~~~
entity Account: (
    ...
    definitions: (
        Name: static("Account - "),
        virtual MyDate: static(@myDate),
        virtual MyDecimal: static(@myDecimal1) format(00.000),
    )
)
~~~