# Templates

## Description

A template is a blueprint for creating records of an entity.

## Definitions

~~~
template <TemplateIdentifier> : (<FieldDefinitionsList>)
~~~

## Notes

* A template contains all the required field definitions of an entity.
* An entity may be defined in more than one templates, which may exist in different repositories.
* A template is used by using `template: <Repository>.<TemplateIdentifier>`.

## Examples

Repository: "SalesTemplates"
~~~
template BigAccounts: (
    Name: ....,
    Industry: ....,
    Site: ...
)
~~~

Repository: "CommonEntities"
~~~
entity Account: (
	template: SalesTemplates.BigAccounts,
    Name: ...,			# The field is defined again (the previous field definition is deleted)
    Industry: ,			# The definition for this field is deleted
)
~~~