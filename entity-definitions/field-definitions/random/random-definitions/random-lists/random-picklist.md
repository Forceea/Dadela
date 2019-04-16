# Random picklist

## Description

Generates random values for picklist fields.

## Definitions

~~~
random type(picklist)
    [ except(<List>) ]
    [ iterations(<PositiveInteger> ]
    [ separator(<String>) ]
~~~

## Notes

* The definition actually inserts a "hidden" parameter value<PicklistValues>.
* The except parameter excludes items from the (default) picklist values.
* The default value of the optional parameter `separator` is <blank>.

## Examples

~~~
random type(picklist) separator(;)
random type(list) value(!Months) except(Feb, June) copies(3)
~~~