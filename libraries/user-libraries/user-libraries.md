# User libraries

## Description

A user library is a _user-defined_ repository with one ore more lists and templates.

## Notes

* A user library is not permitted to contain entity definitions.
* Dadela provides sample libraries for first/last names (name libraries) and addresses (address libraries),
which are user editable.
* A library list is references by `!<LibraryIdentifier>.<ListIdentifier>`, e.g. `!SalesLibrary.MyList`
* A library template is references by `<LibraryIdentifier>.<Templatedentifier>`, e.g. `SalesLibrary.BigAccounts`

## Examples

Repository: "Library1"
~~~
list Notes: (do, re, mi, fa, sol, la, si),
template BigAccounts: (...)
~~~

Repository: "Library2"
~~~
list Months: (Jan, Feb, Mar)
~~~

Repository: "EntityDefinitions"
~~~
list MyList: (!Library1.Notes),

entity Account: (
    ...
   	definitions: (
      	...
      	virtual MyVirtualField1: random type(list) value(!MyList),
      	virtual MyVirtualField2: random type(list) value(!Library2.Months),
      	...
	)
)
~~~