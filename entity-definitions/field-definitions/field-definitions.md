# Field definitions

## Definitions

~~~
<FieldDefinition> := { <FieldIdentifier> | <VirtualFieldIdentifier> } : <FieldDefinitionScript>

<VirtualFieldIdentifier> := virtual <Identifier>

<FieldDefinitionScript> := <command> <script>

<command> := { copy | random | serial | static }

<script> := <cluster> [<cluster>,..]

<cluster> := <parameter>(<argument> [,<argument>,..])
~~~

## Notes

### Execution process

* The field definitions are executed sequentially and additively.
* A field or virtual field may have multiple definitions. 
 
### Field definition types

There are two types of field definitions:

a. **User definitions** are declared by the user.

b. **System definitions** are declared automatically by Dadela in various situations, e.g.
* when it configures the required fields of an entity,
* when it configures a dependent picklist list field.

### Virtual fields

* A virtual field behaves like a "variable"; it creates data but it does not insert/export them.