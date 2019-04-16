# Entity definitions

## Description

An entity definition provides the information of how to generate the entity records.

## Definitions

~~~
<EntityDefinition> := entity <EntityIdentifier> : (
    <Entity variables>
    <Entity attributes>
    definitions : (<FieldDefinitionsList>)
)

<FieldDefinitionsList> := <FieldDefinition> [,<FieldDefinition>]
~~~

## Notes

* An entity definition may include one more local variables (entity variables).
* If an entity attribute is omitted, the global attribute will be applied.

## Examples

~~~
number numberOfAccounts: 1000,

entity Account: (
    string account: Account-,

    alias: MyBigAccounts,
    records: @numberOfAccounts,
    language: German,
    locality: Germany, 
    definitions: (
        Name static value(@account),
        Name random type(number) from(1) to(100) scale(0),
        virtual: MyVirtualField random type(number) from(1) to(100),
        CustomField1 copy field($Name),
        CustomField2 copy field($MyVirtualField)
    )
)
~~~