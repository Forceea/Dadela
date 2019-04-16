# Random strings

## Description

Generates random strings (without <space>), selecting random characters from a list.

## Definitions

~~~
random type(string)
    value(<List>)							# include the list items
	min-length(<PositiveInteger>)			# the minimum number of characters
    max-length(<PositiveInteger>)			# the maximum number of characters
    start-with(<List>)						# the first character of the string
    [ iterations(<PositiveInteger>) ]		# repeat x times
    [ copies(<PositiveInteger>) ]			# copy the result x times
~~~

## Notes

* The default value of the optional parameters `iterations` and `copies` is 1.
* The `max-length` must be greater than `min-length`.

The order of the optional parameters `iterations` and `copies` defines the process as follows:
* If `iterations` is before `copies`, Dadela will generate a random number `x` times
and then will copy the generated concatenated number `y` times.
* If `copies` is before `iterations`, Dadela will copy the generated number `x` times
and then will repeat the process `y` times.

## Examples

~~~
random type(string) value(!Dadela.Digits, !Dadela.Letters)
	min-length(20) max-length(30)
	start-with(!Dadela.Uppercase) copies(2)
~~~