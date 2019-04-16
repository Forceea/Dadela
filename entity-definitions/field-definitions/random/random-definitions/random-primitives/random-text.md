# Random texts

## Description

Generates random texts (with <space and full stops).
The text may or may not have the format of a sentence (first letter: capital, end with: .)

## Definitions

~~~
random type(text)
    value(<List>)									# include the list items
	min-length(<PositiveInteger>)					# the minimum number of characters
    max-length(<PositiveInteger>)					# the maximum number of characters
    start-with( { uppercase | lowercase })			# the first character of the text
    end-with( { fullstop | comma | all | none })	# the last character of the text
    [ iterations(<PositiveInteger>) ]				# repeat x times
    [ copies(<PositiveInteger>) ]					# copy the result x times
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

Generate 10 sentences (starting with uppercase letter and ending with .) from a list of "latinoid" words,
with each sentence have a length between 20 and 30 characters.
~~~
list MyLatinWords: (lorem, ipsum, dolor, sit, amet, tempor, aboreant, instructor, eu, nos, quo, magna, primis,
	labore, usi, virtute, fabellas, vis, duis, scripta, salutandi, laudem, commune, nam, laoreet,
	propriae, corrumpit, ea, partem, inermis, ius, sint, impedit, deterruis, eam, elit, nusquam),
	
random type(text) value(!MyLatinWords) min-length(20) max-length(30)
	start-with(uppercase) end-with(fullstop) iterations(10)
~~~