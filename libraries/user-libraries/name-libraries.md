# Name libraries

## Description

A name library contains first and last names for one ore more combinations of language/locality.

## Definitions

~~~
<NameLibrary> :=
	locality: <LocalityIdentifier> [ (<OtherLocalitiesList>) ],
	<NameDefinition> [,<NameDefinition>]

<NameDefinition> := list <Identifier> (
	language: <LanguageIdentifier>,
	firstNames: (<FirstName> [,<FirstName>]),
	lastNames: (<LastName> [,<LastName>])
)

<FirstName> := { (<Name>, <Gender>) | <Name> }

<LastName> := { (<Name>, <Gender>) | <Name> }

<Gender> := { male | female }
~~~

## Notes

* A name library is user editable.
* The locality is considered a member of the localities in the optional <OtherLocalitiesList>. 
* The suggested format for the identifier of address libraries is `Names<CountryCode>`, e.g. `NamesUs`.
* If `Gender` is omitted, the first/last name is not related to a specific gender.
For example, in English a last name is not related to a specific gender, while in Greek a last name is related.

## Examples

Repository: "NamesUs"
~~~
locality: United States (North America, America),

list NamesInEnglish: (
	language: English,
	firstNames: (
		(FirstName1, male),
		(FirstName2, female),
		...
	),
	lastNames: (LastName1, LastName2, ...)
)
~~~