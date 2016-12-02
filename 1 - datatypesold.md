# Datatypes

## Scalar variables

An unusual feature of Julia is that it allows variable names to include a subset of Unicode symbols, allowing a variable to be represented e.g. by a greek letter.

In most Julia development environments (including the consol\), to input in the script the greek letter you can use a LaTeX-like syntax, typing `\` and then the LaTeX name for the symbol, e.g. `\alpha` for α.
Using LaTeX syntax, you can also add subscripts, superscripts and decorators.

The main types of scalar you will use are `Int64`, `Float64`, `Char` (e.g. `x = 'a'`), `String` \(e.g. `x="abc"`\) and `Bool`.
The default if you do not specify is `Float64`.



## Strings

### Concatenation

* Concatenation operator: `*`
* function `string(str1,str2,str3)`
* combine string variables in a bigger one using the dollar symbol: `a = "$str1 is a string and $int1 is an integer"`

The first method doesn't authomatically cast integer and floats to strings.

## Arrays (lists)

Empty (zero-elements) arrays: `a = []` (or `a = Int64[]`)
5-elements zeros array:`a=zeros(5)` (or `a=zeros(Int64,5)`) (same with ones)

Column vector \('Vector' container\) : `a = [1;2;3]` or `a=[1,2,3]` \(common\)
Row vector \('Matrix' container\) : `a = [1 2 3]`

Reference to an element of an array\/vector\/matrix: `a[1]` \(you can use also the keyword `end`, but not `begin`\)

Slice syntax \[from:step:to\] is generally supported.

Push an element to the end of a: `push!(a,b)`

To append the elements of b to a: `append!(a,b)`
\(if b is a scalar obviously push! and append! are the same\)

Remove an element from the end: `pop!(a)`

Add an element at the beginning \(left\): `unshift!(a,1)`

Removing an element at the beginning \(left\) : `shift!(a)`

Sorting: `sort!(a)` or `sort(a)` \(depending if we want modify or not the original array\)

Reversing an arry: `a[end:-1:1]`

Checking for existence: `in(1, a)`

Getting the length: `length(a)`

## Turples

Use turples to have a list of immutable elements: `a = (1,2,3)` or even without parenthesis `a = 1,2,3`

## Dictionaries

Dictionaries store mappings from key to value. They have an apparently random sorting.

Empty \(zero-elements\) dictionary: `mydict = Dict()`

Initialize a dictionary with values: `mydict = Dict('a'=>1, 'b'=>2, 'c'=>3)`

Look up values: `mydict['a']` \(raise an error if looked-up value doesn't exist\)
Look up value with a default value for non-existing key: `get(mydict,'a',0)`

Get all keys: `keys(mydict)` \(the result is an iterator, not a list\)
Get all values: `values(mydict)` \(result is again an iterator\)

Check if a key exists: `haskey(mydict, 'a')`
Check if a given key\/value pair exists \(that it, if the key exists and has that specific value\): `in(('a' => 1), mydict)`

Iterate trough a dictionary:

```
for (k,v) in mydict
   println("$k is $v")
end
```

## Sets

Use Sets to represent collections of unordered, unique values

Empty \(zero-elements\) set: `a = Set()`

Initialize a set with values: `a = Set([1,2,2,3,4])`

Set intersection, union, and difference: `intersect(set1,set2)`, `union(set1,set2)`, `setdiff(set1,set2)`
