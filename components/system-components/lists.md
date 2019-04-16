# Lists

## Scope

A list includes one or more items.
A list item may a component like be a <String>, a <FieldDefinition> or an <EntityDefinition>.

## Definitions
~~~
list <Identifier> ( <item> [,<item>,.. ]

<item> := { <LiteralValue> | <Component> }
~~~

## Notes
* An empty list is valid, e.g. `list MyEmptyList (),`.
* The suggested capitalization for lists is PascalCase, e.g. `MySource`.
* A list is referenced using `!<dentifier>`, e.g. `!MyList`.

## Examples
~~~
use library: (MyLibrary1, MyLibrary2),

list Notes: (do, re, mi, fa, sol, la, si),
list MyList1: (one, two or three, !Notes),					# get items from list Notes
list MyList2: (one, "two, three or four", !Notes),
list MyList3: (!MyLibrary.MusicalNotes),					# get items from a library
list MyList4: (!MyList1, @myString),						# get items from a list and a variable
~~~