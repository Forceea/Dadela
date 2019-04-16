# Random date

## Description

Generates random dates.

## Definitions

~~~
random type(date) from(<Date>) to(<Date>)
~~~

## Notes

* Use the format YYYY-MM-DD for the argument of `from` and `to` parameters.
* If the `to` argument is less than or equal to the `from` argument, dadela will raise an error.

## Examples

~~~
date startDate: 2018-01-01 15:22:00,
date endDate: 2018-12-31,

entity Account: (
    alias: MyBigAccounts,
    definitions: (
        virtual Date1: random type(date) from(2018-01-01) to(2018-12-31),
        virtual Date2: random type(date) from(@startDate) to(2018-12-31),
        virtual Date3; random type(date) from(@startDate) to(@endDate)
    )
)
~~~