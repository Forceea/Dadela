# Copy field

## Description 
 
Copies the value of a field in the same record.

## Definitions

~~~
copy field(<ReferenceField>) [ from(<LookupField>) ]
~~~

## Notes

* The <ReferenceField> can be an entity field or a virtual field.
* The <ReferenceField> may not be defined in the entity definition, e.g. a field that may be populated automatically.
* If the <ReferenceField> is a lookup ID which refers to <LookupEntity> entity,
 the <LookupField> of the optional `from` parameter refers to a field of this entity.
 
 ## Examples
 
~~~
entity Account: (	
    ...
    definitions: (
    	Name: static value(Account-),
        Opportunity: random lookup(Opportunity) source(MySource),
        virtual MyField1: copy(Name),
        virtual MyField2: copy(Opportunity) from(Name),
		...
    )
)
~~~

Result 1: The `copy(Name)` definition will copy the value
of the `Name` field of the same `Account` record to `MyField1`.

Result 2: The `copy(Opportunity)` definition will copy the value
of the `Name` field of `Opportunity` entity to `MyField2`.