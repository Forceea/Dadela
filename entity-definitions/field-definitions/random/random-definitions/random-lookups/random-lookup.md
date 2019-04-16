# Random lookup

## Description

Generates random IDs from a lookup entity.

## Definitions

~~~
random lookup(<LookupEntity>) source(<SourceIdentifier>)

<SourceIdentifier> := { Dadela | <UserDefinedSource> }

random lookup(<LookupEntity>) source(Dadela) group(<Groupidentifier>)
~~~

## Notes

* If we insert records using the `group` parameter, we can retrieve the lookup IDs of this group
using the `random lookup group` construction.

## Examples

~~~
entity Account: (
	alias: MyAccounts,
    definitions: ( ... )
),
insert MyAccounts: (destination(MyDest) group(GroupA)),

entity Opportunity from templateOpp: (
	alias: MyOpportunities,
    definitions: (
        AccountId: random lookup(Account) source(Dadela) group(GroupA),
        ...
    )
)
insert MyOpportunities: (destination(MyDest) group(GroupB)),
~~~