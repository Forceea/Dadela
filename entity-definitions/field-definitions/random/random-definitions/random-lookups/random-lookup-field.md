# Random lookup field

## Description

Generates random IDs from from records of the lookup object,

## Definitions

~~~
random lookup(<LookupEntity>)
	field(<FieldIdentifier>)
	{ value(<List>) | except(<List>) }
	source(<SourceIdentifier>)

random lookup(<LookupEntity>)
	field(<FieldIdentifier>)
	{ value(<List>) | except(<List>) }
	source(Dadela)
	group(<Groupidentifier>)
	
<SourceIdentifier> := { Dadela | <UserDefinedSource> }
~~~

## Notes

* If we insert records using the `group` parameter, we can retrieve the lookup IDs of this group
using the `random lookup group` construction.
* The `value` parameter retrieves the lookup records
under the restriction that a specific field has one or more given values.
This behaves like `WHERE field IN ('value1', 'value2', ..)`.
* The `except` parameter retrieves the lookup records
under the restriction that a specific field does not have one or more given values.
This behaves like `WHERE field NOT IN ('value1', 'value2', ..)`.

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
insert MyAccounts: (destination(MyDest) group(GroupA)),

entity Opportunity : (
	template: MyTemplate.Opps,
	alias: MyOpportunities,
    definitions: (
        AccountId: random lookup(Account)
        	field(Industry) except(Technology, Financials) 
        	source(Dadela) group(GroupA),
        ...
    )
)
insert MyOpportunities: (destination(MyDest) group(GroupB)),
~~~