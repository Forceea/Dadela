# Random dates with time

## Description

Generates random dates with time.

## Definitions

~~~
random type(datetime) from( {<Date> | <Datetime> } ) to( { <Date> | <Datetime> } )
~~~

## Notes

* Use the format `YYYY-MM-DD` (for Date) and `YYYY-MM-DD HH:MM:SS` (for Datetime)
for the argument of `from` and `to` parameters.
* Any combination of Date and Datetime arguments are valid, e.g. from(2018-01-01 01:01:01) to(2018-01-05).
* If the `from` parameter has a Date argument, e.g. from(2018-01-01),
the Date argument will be parsed as start of the day (2018-01-01 00:00:00).
* If the `to` parameter has a Date argument, e.g. to(2018-01-01),
the Date argument will be parsed as end of the day (2018-01-01 23:59:59).
* If the `to` argument is less than or equal to the `from` argument, Dadela will raise an error.

## Examples

~~~
date startDate: 2018-01-01 15:22:00,
date endDate: 2018-12-31,

entity Account: (
    alias: MyBigAccounts,
    definitions: (
        virtual Date1: random type(datetime) from(2018-01-01) to(2018-12-31),
        virtual Date2: random type(datetime) from(@startDate) to(2018-12-31),
        virtual Date3: random type(datetime) from(@startDate) to(@endDate)
    )
)
~~~