# Random email addresses

## Description

Generates random email addresses.

## Definitions

~~~
random type(email)
    username(<Source>) [ iterations(<PositiveInteger> ] [ copies(<PositiveInteger>) ]
    domain(<Source>) [ iterations(<PositiveInteger> ] [ copies(<PositiveInteger>) ]
    toplevel(<Source>)

<Source> := { <String> | <Field> }
~~~

## Notes

The order of the optional parameters `iterations` and `copies` defines the process as follows:
* If `iterations` is before `copies`, Dadela will generate a random number `x` times
and then will copy the generated concatenated number `y` times.
* If `copies` is before `iterations`, Dadela will copy the generated number `x` times
and then will repeat the process `y` times.

## Examples

~~~
number start: 1,
number numDomains: 5,
list Usernames: (ca, lo, sa, ri, be, no, ve, ta, la),
list Domains: (do, re, mi, fa, sol, la, si),
list TopLevelDomains: (com, co.uk, gr),

entity Account: (
    alias: MyBigAccounts,
    records: 200,
    definitions: (
        virtual Username: random type(list) value(!Usernames) iterations(4),
        virtual Username: random type(number) from(@start) to(100),
        virtual Username: static value(comp),
        virtual Username: serial type(number) from(@start) step(1),
        virtual Domain: random type(list) value(!Domains) iterations(5),
        virtual TopLevelDomain: random type(list) value(!TopLevelDomains),
        Email: random type(email) username($Username) domain($Domain) toplevel($TopLevelDomain),
    )
)
~~~