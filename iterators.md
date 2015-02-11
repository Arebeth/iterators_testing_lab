##Descriptions of Iterators

###Instructions
Below you will find a list of methods. In the space provided below each, please provide a brief description of what this method does based upon your review of the Docs. 

###Array methods:
May be helpful to look in [Enumerable](http://ruby-doc.org/core-2.2.0/Enumerable.html) as well...

####select:
	select { |item| block } → new_ary
		- if the item is evaluated by the block to be true, it is passed to the new array.
		- returns a new array with the selected items

####reject:
	reject {|item| block } → new_ary
		- if the item is evaluated by the block to be false, it is passed to the new array.
		- returns a new array with the rejected items
####map:
	map { |item| block } → new_ary
		- runs block on every item.
		- returns a new array with values returned by block

####detect:
	detect(ifnone = nil) { |obj| block } → obj or nil
		- runs block on all enums (returns truth), or "ifnone" if no block (returns nil)
		- returns first truthy value or nil.

####inject:
	inject(initial, sym) → obj
	inject(sym) → obj
	inject(initial) { |memo, obj| block } → obj
	inject { |memo, obj| block } → obj
		- similar to reduce, only uses block
		- runs block on all enums * applies method
		- eg: (5..10).inject(1) {|product, n| product * n} => 151200
		- returns value 

####partition:
	partition { |obj| block } → [ true_array, false_array ]
		- returns a 2D array - containing one sub-array for true values and one sub-array for falsey values
	
####sort:
	sort → array
	sort { |a, b| block } → array
		- returns an array with the items sorted
	
	also, sort_by { |obj| block } → array
		- sorts by block specified
		- eg: %w{apple pear fig}.sort_by { |word| word.length}

####one?:
	one? [{ |obj| block }] → true or false
		- each item is passed to the block. if exactly one item evaluates to true, returns true.
		- returns true or false

####none?:
	none? [{ |obj| block }] → true or false
		- each item is passed to the block. if none of the items evaluate to true, returns true.
		- returns true or false

####all:
	all? [{ |obj| block } ] → true or false
		- each item is passed to the block. if all of the items evaluate to true (never false or nil), returns true.
		- returns true or false

####empty?:
	empty? → true or false
		- Array method - if array is empty, returns true.

####eql?:
	eql?(other) → true or false
		- if obj or array have same content, returns true. 

####include?:
	include?(object) → true or false
		- Array method - if one of the method parameters is in the array, return true, otherwise return false.

####nil?:
	nil? → true
		- if the object is nil(The class of the singleton object nil), return true.

###Hash methods:

####key?:
	key?(key) → true or false
		- if they key you're passing is in the hash, return true
		- returns true or false

####keys:
	keys → array
		- makes a new array of just the keys (not the values)

####delete:
	delete(key) → value click to toggle source
	delete(key) {| key | block } → value
		- deletes the key/value pair & returns the value of they key deleted. keys/values not referenced stay in the array.
		- returns the value of the key you deleted

####delete_if:
	delete_if {| key, value | block } → hsh click to toggle source
	delete_if → an_enumerator
		- deletes the key/value pair if the block evaluates the key to true.
		- returns the value of they key you deleted