# System libraries

## Description

A system library is a _system-defined_ repository with useful lists (e.g. musical notes or days of week)
and cannot be modified by the user.

## Notes

The standard system library has the identifier `Dadela` and includes the following lists:
* Digits: (0, .. ,9)
* Lowercase: (a , .., z)
* Uppercase: (A, .., Z)
* Letters: (Lowercase, Uppercase)
* LettersAndDigits: (Letters, Digits)
* Months: (January, .., December)
* Days: (Sunday, .., Saturday)
* MusicalNotes: (do, re, mi, fa, sol, la, si)

## Examples

Repository: "SalesEntities"
~~~
list MyList: (!Dadela.Notes)
~~~