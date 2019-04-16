# Address libraries

## Description

An address library contains addresses for one ore more combinations of language/locality.

## Definitions

~~~
<AddressLibrary> :=
	locality: <LocalityIdentifier> (<OtherLocalitiesList>),
	<AddressesDefinition> [ ,<AddressesDefinition> ]

<AddressesDefinition> := list <Identifier> (
	language: <Language>,
	country: <Country>,
	number: ( { left | right }, [ from(<FirstNumber>) ] to(<LastNumber) ),
	addresses: (<Address> [,<Address>])
)

<Address> := (<Street>, <PostalCode>, <City>, <StateOrProvince>)
~~~

## Notes
* An address library is user editable.
* The suggested format for the identifier of address libraries is `Addresses<CountryCode>`, e.g. `AddressesUs`.
* The `numberPosition` defines if the street number will be on the left or on the right of the street.
* The `numberRange` defines the first and last street number, e.g. `from(1) to(50)`.

## Examples

Repository: "AddressesFr"
~~~
locality: France (North Europe, European Union, Europe),

list AddressesInFrench: (
	language: French,
	country: France,
	number: (left, from(1) to(50)),
	addresses: (
		(Street1, PostalCode1, City1, StateOrProvince1),
		(Street2, PostalCode2, City2, StateOrProvince2),
		...
	)
),
list AddressesInEnglish: (
	language: English,
	country: France,
	number: (left, to(50)), 	# default: from(1)
	addresses: (
		(Street1, PostalCode1, City1, StateOrProvince1),
		(Street2, PostalCode2, City2, StateOrProvince2),
		...
	)
)
~~~