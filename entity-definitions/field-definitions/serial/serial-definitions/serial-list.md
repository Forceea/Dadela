# Serial list

## Description

Generates serial list items.

## Definitions

~~~
serial type(list)
    value(<List>)
    [ start(<ListItem>) ]                 # start from this item
    [ except(<List>) ]                    # don't include these items
~~~

## Notes

* The `except` parameter defines the excluded list items.
* The `start` parameter defines the first list item.
* After the last list item, the next item will be the first available list item.

## Examples

~~~
list List1: (three),
...
serial type(list) value(one, two, three, four, five) start(two) exclude(!List1, four),
~~~
Result: two, five, one, two, ...