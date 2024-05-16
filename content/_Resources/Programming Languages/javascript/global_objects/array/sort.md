Array.prototype.sort()
======================


The `sort()` method of [`Array`](../array) instances sorts the elements
of an array *[in
place](https://en.wikipedia.org/wiki/In-place_algorithm)* and returns
the reference to the same array, now sorted. The default sort order is
ascending, built upon converting the elements into strings, then
comparing their sequences of UTF-16 code units values.

The time and space complexity of the sort cannot be guaranteed as it
depends on the implementation.

To sort the elements in an array without mutating the original array,
use [`toSorted()`](tosorted).



Try it 
------






Syntax
------




[js]


```js
sort()
sort(compareFn)
```





### Parameters



[`compareFn`](#comparefn) [Optional]

:   A function that defines the sort order. The return value should be a
    number whose sign indicates the relative order of the two elements:
    negative if `a` is less than `b`, positive if `a` is greater than
    `b`, and zero if they are equal. `NaN` is treated as `0`. The
    function is called with the following arguments:

    [`a`](#a)

    :   The first element for comparison. Will never be `undefined`.

    [`b`](#b)

    :   The second element for comparison. Will never be `undefined`.

    If omitted, the array elements are converted to strings, then sorted
    according to each character\'s Unicode code point value.




### Return value 


The reference to the original array, now sorted. Note that the array is
sorted *[in place](https://en.wikipedia.org/wiki/In-place_algorithm)*,
and no copy is made.




Description
-----------


If `compareFn` is not supplied, all non-`undefined` array elements are
sorted by converting them to strings and comparing strings in UTF-16
code units order. For example, \"banana\" comes before \"cherry\". In a
numeric sort, 9 comes before 80, but because numbers are converted to
strings, \"80\" comes before \"9\" in the Unicode order. All `undefined`
elements are sorted to the end of the array.

The `sort()` method preserves empty slots. If the source array is
[sparse](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections#sparse_arrays),
the empty slots are moved to the end of the array, and always come after
all the `undefined`.

 
**Note:** In UTF-16, Unicode characters above `\uFFFF` are encoded as
two surrogate code units, of the range `\uD800` - `\uDFFF`. The value of
each code unit is taken separately into account for the comparison. Thus
the character formed by the surrogate pair `\uD855\uDE51` will be sorted
before the character `\uFF3A`.


If `compareFn` is supplied, all non-`undefined` array elements are
sorted according to the return value of the compare function (all
`undefined` elements are sorted to the end of the array, with no call to
`compareFn`).


  `compareFn(a, b)` return value   sort order
  -------------------------------- ------------------------------------
  \> 0                             sort `a` after `b`, e.g. `[b, a]`
  \< 0                             sort `a` before `b`, e.g. `[a, b]`
  === 0                            keep original order of `a` and `b`


So, the compare function has the following form:



[js]


```js
function compareFn(a, b) {
  if (a is less than b by some ordering criterion) {
    return -1;
  } else if (a is greater than b by the ordering criterion) {
    return 1;
  }
  // a must be equal to b
  return 0;
}
```


More formally, the comparator is expected to have the following
properties, in order to ensure proper sort behavior:

-   *Pure*: The comparator does not mutate the objects being compared or
    any external state. (This is important because there\'s no guarantee
    *when* and *how* the comparator will be called, so any particular
    call should not produce visible effects to the outside.)
-   *Stable*: The comparator returns the same result with the same pair
    of input.
-   *Reflexive*: `compareFn(a, a) === 0`.
-   *Anti-symmetric*: `compareFn(a, b)` and `compareFn(b, a)` must both
    be `0` or have opposite signs.
-   *Transitive*: If `compareFn(a, b)` and `compareFn(b, c)` are both
    positive, zero, or negative, then `compareFn(a, c)` has the same
    positivity as the previous two.

A comparator conforming to the constraints above will always be able to
return all of `1`, `0`, and `-1`, or consistently return `0`. For
example, if a comparator only returns `1` and `0`, or only returns `0`
and `-1`, it will not be able to sort reliably because *anti-symmetry*
is broken. A comparator that always returns `0` will cause the array to
not be changed at all, but is reliable nonetheless.

The default lexicographic comparator satisfies all constraints above.

To compare numbers instead of strings, the compare function can subtract
`b` from `a`. The following function will sort the array in ascending
order (if it doesn\'t contain `NaN`):



[js]


```js
function compareNumbers(a, b) {
  return a - b;
}
```


The `sort()` method is [generic](../array#generic_array_methods). It
only expects the `this` value to have a `length` property and
integer-keyed properties. Although strings are also array-like, this
method is not suitable to be applied on them, as strings are immutable.




Examples
--------



### Creating, displaying, and sorting an array 


The following example creates four arrays and displays the original
array, then the sorted arrays. The numeric arrays are sorted without a
compare function, then sorted using one.



[js]


```js
const stringArray = ["Blue", "Humpback", "Beluga"];
const numberArray = [40, 1, 5, 200];
const numericStringArray = ["80", "9", "700"];
const mixedNumericArray = ["80", "9", "700", 40, 1, 5, 200];

function compareNumbers(a, b) {
  return a - b;
}

stringArray.join(); // 'Blue,Humpback,Beluga'
stringArray.sort(); // ['Beluga', 'Blue', 'Humpback']

numberArray.join(); // '40,1,5,200'
numberArray.sort(); // [1, 200, 40, 5]
numberArray.sort(compareNumbers); // [1, 5, 40, 200]

numericStringArray.join(); // '80,9,700'
numericStringArray.sort(); // ['700', '80', '9']
numericStringArray.sort(compareNumbers); // ['9', '80', '700']

mixedNumericArray.join(); // '80,9,700,40,1,5,200'
mixedNumericArray.sort(); // [1, 200, 40, 5, '700', '80', '9']
mixedNumericArray.sort(compareNumbers); // [1, 5, '9', 40, '80', 200, '700']
```





### Sorting array of objects 


Arrays of objects can be sorted by comparing the value of one of their
properties.



[js]


```js
const items = [
  { name: "Edward", value: 21 },
  { name: "Sharpe", value: 37 },
  { name: "And", value: 45 },
  { name: "The", value: -12 },
  { name: "Magnetic", value: 13 },
  { name: "Zeros", value: 37 },
];

// sort by value
items.sort((a, b) => a.value - b.value);

// sort by name
items.sort((a, b) => {
  const nameA = a.name.toUpperCase(); // ignore upper and lowercase
  const nameB = b.name.toUpperCase(); // ignore upper and lowercase
  if (nameA < nameB) {
    return -1;
  }
  if (nameA > nameB) {
    return 1;
  }

  // names must be equal
  return 0;
});
```





### Sorting non-ASCII characters 


For sorting strings with
non-[ASCII](https://developer.mozilla.org/en-US/docs/Glossary/ASCII)
characters, i.e. strings with accented characters (e, é, è, a, ä, etc.),
strings from languages other than English, use
[`String.prototype.localeCompare()`](../string/localecompare). This
function can compare those characters so they appear in the right order.



[js]


```js
const items = ["réservé", "premier", "communiqué", "café", "adieu", "éclair"];
items.sort((a, b) => a.localeCompare(b));

// items is ['adieu', 'café', 'communiqué', 'éclair', 'premier', 'réservé']
```





### Sorting with map 


The `compareFn` can be invoked multiple times per element within the
array. Depending on the `compareFn`\'s nature, this may yield a high
overhead. The more work a `compareFn` does and the more elements there
are to sort, it may be more efficient to use [`map()`](map) for sorting.
The idea is to traverse the array once to extract the actual values used
for sorting into a temporary array, sort the temporary array, and then
traverse the temporary array to achieve the right order.



[js]


```js
// the array to be sorted
const data = ["delta", "alpha", "charlie", "bravo"];

// temporary array holds objects with position and sort-value
const mapped = data.map((v, i) => {
  return { i, value: someSlowOperation(v) };
});

// sorting the mapped array containing the reduced values
mapped.sort((a, b) => {
  if (a.value > b.value) {
    return 1;
  }
  if (a.value < b.value) {
    return -1;
  }
  return 0;
});

const result = mapped.map((v) => data[v.i]);
```


There is an open source library available called
[mapsort](https://github.com/Pimm/mapsort) which applies this approach.




### sort() returns the reference to the same array 


The `sort()` method returns a reference to the original array, so
mutating the returned array will mutate the original array as well.



[js]


```js
const numbers = [3, 1, 4, 1, 5];
const sorted = numbers.sort((a, b) => a - b);
// numbers and sorted are both [1, 1, 3, 4, 5]
sorted[0] = 10;
console.log(numbers[0]); // 10
```


In case you want `sort()` to not mutate the original array, but return a
[shallow-copied](https://developer.mozilla.org/en-US/docs/Glossary/Shallow_copy)
array like other array methods (e.g. [`map()`](map)) do, use the
[`toSorted()`](tosorted) method. Alternatively, you can do a shallow
copy before calling `sort()`, using the [spread
syntax](../../operators/spread_syntax) or [`Array.from()`](from).



[js]


```js
const numbers = [3, 1, 4, 1, 5];
// [...numbers] creates a shallow copy, so sort() does not mutate the original
const sorted = [...numbers].sort((a, b) => a - b);
sorted[0] = 10;
console.log(numbers[0]); // 3
```





### Sort stability 


Since version 10 (or ECMAScript 2019), the specification dictates that
`Array.prototype.sort` is stable.

For example, say you had a list of students alongside their grades. Note
that the list of students is already pre-sorted by name in alphabetical
order:



[js]


```js
const students = [
  { name: "Alex", grade: 15 },
  { name: "Devlin", grade: 15 },
  { name: "Eagle", grade: 13 },
  { name: "Sam", grade: 14 },
];
```


After sorting this array by `grade` in ascending order:



[js]


```js
students.sort((firstItem, secondItem) => firstItem.grade - secondItem.grade);
```


The `students` variable will then have the following value:



[js]


```js
[
  { name: "Eagle", grade: 13 },
  { name: "Sam", grade: 14 },
  { name: "Alex", grade: 15 }, // original maintained for similar grade (stable sorting)
  { name: "Devlin", grade: 15 }, // original maintained for similar grade (stable sorting)
];
```


It\'s important to note that students that have the same grade (for
example, Alex and Devlin), will remain in the same order as before
calling the sort. This is what a stable sorting algorithm guarantees.

Before version 10 (or ECMAScript 2019), sort stability was not
guaranteed, meaning that you could end up with the following:



[js]


```js
[
  { name: "Eagle", grade: 13 },
  { name: "Sam", grade: 14 },
  { name: "Devlin", grade: 15 }, // original order not maintained
  { name: "Alex", grade: 15 }, // original order not maintained
];
```





### Sorting with non-well-formed comparator 


If a comparing function does not satisfy all of purity, stability,
reflexivity, anti-symmetry, and transitivity rules, as explained in the
[description](#description), the program\'s behavior is not
well-defined.

For example, consider this code:



[js]


```js
const arr = [3, 1, 4, 1, 5, 9];
const compareFn = (a, b) => (a > b ? 1 : 0);
arr.sort(compareFn);
```


The `compareFn` function here is not well-formed, because it does not
satisfy anti-symmetry: if `a > b`, it returns `1`; but by swapping `a`
and `b`, it returns `0` instead of a negative value. Therefore, the
resulting array will be different across engines. For example, V8 (used
by Chrome, Node.js, etc.) and JavaScriptCore (used by Safari) would not
sort the array at all and return `[3, 1, 4, 1, 5, 9]`, while
SpiderMonkey (used by Firefox) will return the array sorted ascendingly,
as `[1, 1, 3, 4, 5, 9]`.

However, if the `compareFn` function is changed slightly so that it
returns `-1` or `0`:



[js]


```js
const arr = [3, 1, 4, 1, 5, 9];
const compareFn = (a, b) => (a > b ? -1 : 0);
arr.sort(compareFn);
```


Then V8 and JavaScriptCore sorts it descendingly, as
`[9, 5, 4, 3, 1, 1]`, while SpiderMonkey returns it as-is:
`[3, 1, 4, 1, 5, 9]`.

Due to this implementation inconsistency, you are always advised to make
your comparator well-formed by following the five constraints.




### Using sort() on sparse arrays 


Empty slots are moved to the end of the array.



[js]


```js
console.log(["a", "c", , "b"].sort()); // ['a', 'b', 'c', empty]
console.log([, undefined, "a", "b"].sort()); // ["a", "b", undefined, empty]
```





### Calling sort() on non-array objects 


The `sort()` method reads the `length` property of `this`. It then
collects all existing integer-keyed properties in the range of `0` to
`length - 1`, sorts them, and writes them back. If there are missing
properties in the range, the corresponding trailing properties are
[deleted](../../operators/delete), as if the non-existent properties are
sorted towards the end.



[js]


```js
const arrayLike = {
  length: 3,
  unrelated: "foo",
  0: 5,
  2: 4,
};
console.log(Array.prototype.sort.call(arrayLike));
// { '0': 4, '1': 5, length: 3, unrelated: 'foo' }
```




Specifications
--------------


  -------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-array.prototype.sort]](https://tc39.es/ecma262/multipage/indexed-collections.html#sec-array.prototype.sort)

  -------------------------------------------------------------------------------------------------------------------------


Browser compatibility 
---------------------




Desktop

Mobile

Server

Chrome

Edge

Firefox

Opera

Safari

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

WebView Android

Deno

Node.js

`sort`

1

12

1

4

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

`stable`

70

79

3

57

10.1

70

4

49

10.3

10.0

70

1.0

12.0.0


See also 
--------


-   [Polyfill of `Array.prototype.sort` with modern behavior like stable
    sort in
    `core-js`](https://github.com/zloirock/core-js#ecmascript-array)
-   [Indexed
    collections](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections)
    guide
-   [`Array`](../array)
-   [`Array.prototype.reverse()`](reverse)
-   [`Array.prototype.toSorted()`](tosorted)
-   [`String.prototype.localeCompare()`](../string/localecompare)
-   [`TypedArray.prototype.sort()`](../typedarray/sort)
-   [Getting things sorted in V8](https://v8.dev/blog/array-sort) on
    v8.dev (2018)
-   [Stable `Array.prototype.sort`](https://v8.dev/features/stable-sort)
    on v8.dev (2019)
-   [`Array.prototype.sort`
    stability](https://mathiasbynens.be/demo/sort-stability) by Mathias
    Bynens




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/sort>

