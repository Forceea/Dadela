# Entity attributes

## Description

An entity attribute is a property of an entity.

## Definitions

~~~
<EntityAttribute> := { alias | records | language | locality | seed } : <Value>
~~~

## Notes

* None.

## Examples

~~~
entity Account: (
    alias: BigAccounts,
    language: English,
    locality: United States,
    records: @numOfRecords,
    seed: @seed + 1,
   	definitions: (
      	...
	)
)
~~~