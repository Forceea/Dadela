# Global attributes

## Description

A global attribute is the default entity attribute for all entity definitions of a repository.

## Definitions
~~~
<GlobalAttribute> := { records | language | locality | seed } : <Value>
~~~

## Notes

* A global attribute can be defined once per repository, after the library definitions (if any).

## Examples

Repository: "Repo1"
~~~
language: Italian,
locality: Italy,
records: 100,
seed: -2,
...
~~~