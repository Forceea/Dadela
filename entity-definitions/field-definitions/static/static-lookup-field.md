# Static lookup field

## Description

Generates IDs from the first record of the lookup object for which a field has a given value.

## Definitions

~~~
static lookup(<LookupEntity>)
	field(<FieldIdentifier>)
	value(<Value>)
	source(<SourceIdentifier>)

static lookup(<LookupEntity>)
	field(<FieldIdentifier>)
	value(<Value>)
	source(Dadela) group(<Groupidentifier>)
	
<SourceIdentifier> := { Dadela | <UserDefinedSource> }
~~~

## Notes

* If we insert records using the `group` parameter, we can retrieve the lookup IDs of this group
using the `static lookup group` construction.

## Examples

~~~
entity Account: (
	alias: MyAccounts,
    definitions: (
    	...
    	Industry: random type(picklist),
    	...
    )
),
insert MyAccounts: (destination(MyDestination1) group(GroupA)),

entity Opportunity from templateOpp: (
	template: MyTemplates.SmallOpportunities 
	alias: MySmallOpportunities,
    definitions: (
        AccountId: static lookup(Account)
        	field(Industry) value(Technology) source(Dadela) group(GroupA),
        ...
    )
),
insert MyOpportunities: (destination(MyDestination1) group(GroupB)),
~~~