Map.groupBy()
=============

[Limited availability]
---------------------------------

 
This feature is not Baseline because it does not work in some of the
most widely-used browsers.

-   [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-evolution-on-mdn/)
-   [See full compatibility](#browser_compatibility)
-   [Report
    feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FJavaScript%2FReference%2FGlobal_Objects%2FMap%2FgroupBy&level=not)


 
 
**Note:** In some versions of some browsers, this method was implemented
as the method `Array.prototype.groupToMap()`. Due to web compatibility
issues, it is now implemented as a static method. Check the [browser
compatibility table](#browser_compatibility) for details.


The `Map.groupBy()` static method groups the elements of a given
iterable using the values returned by a provided callback function. The
final returned [`Map`](../map) uses the unique values from the test
function as keys, which can be used to get the array of elements in each
group.

The method is primarily useful when grouping elements that are
associated with an object, and in particular when that object might
change over time. If the object is invariant, you might instead
represent it using a string, and group elements with
[`Object.groupBy()`](../object/groupby).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
Map.groupBy(items, callbackFn)
```




 
### Parameters

 

[`items`](#items)

:   An [iterable](../../iteration_protocols#the_iterable_protocol) (such
    as an [`Array`](../array)) whose elements will be grouped.

[`callbackFn`](#callbackfn)

:   A function to execute for each element in the iterable. It should
    return a value
    ([object](https://developer.mozilla.org/en-US/docs/Glossary/Object)
    or
    [primitive](https://developer.mozilla.org/en-US/docs/Glossary/Primitive))
    indicating the group of the current element. The function is called
    with the following arguments:

    [`element`](#element)

    :   The current element being processed.

    [`index`](#index)

    :   The index of the current element being processed.



 
### Return value 

 
A [`Map`](../map) object with keys for each group, each assigned to an
array containing the elements of the associated group.



 
Description
-----------

 
`Map.groupBy()` calls a provided `callbackFn` function once for each
element in an iterable. The callback function should return a value
indicating the group of the associated element. The values returned by
`callbackFn` are used as keys for the [`Map`](../map) returned by
`Map.groupBy()`. Each key has an associated array containing all the
elements for which the callback returned the same value.

The elements in the returned [`Map`](../map) and the original iterable
are the same (not [deep
copies](https://developer.mozilla.org/en-US/docs/Glossary/Deep_copy)).
Changing the internal structure of the elements will be reflected in
both the original iterable and the returned [`Map`](../map).

This method is useful when you need to group information that is related
to a particular object that might potentially change over time. This is
because even if the object is modified, it will continue to work as a
key to the returned `Map`. If you instead create a string representation
for the object and use that as a grouping key in
[`Object.groupBy()`](../object/groupby), you must maintain the mapping
between the original object and its representation as the object
changes.

 
**Note:** To access the groups in the returned `Map`, you must use the
same object that was originally used as a key in the `Map` (although you
may modify its properties). You can\'t use another object that just
happens to have the same name and properties.


`Map.groupBy` does not read the value of `this`. It can be called on any
object and a new [`Map`](../map) instance will be returned.



 
Examples
--------


 
### Using Map.groupBy() 

 
First we define an array containing objects representing an inventory of
different foodstuffs. Each food has a `type` and a `quantity`.

 
 
[js]


```js
const inventory = [
  { name: "asparagus", type: "vegetables", quantity: 9 },
  { name: "bananas", type: "fruit", quantity: 5 },
  { name: "goat", type: "meat", quantity: 23 },
  { name: "cherries", type: "fruit", quantity: 12 },
  { name: "fish", type: "meat", quantity: 22 },
];
```


The code below uses `Map.groupBy()` with an arrow function that returns
the object keys named `restock` or `sufficient`, depending on whether
the element has `quantity < 6`. The returned `result` object is a `Map`
so we need to call `get()` with the key to obtain the array.

 
 
[js]


```js
const restock = { restock: true };
const sufficient = { restock: false };
const result = Map.groupBy(inventory, ({ quantity }) =>
  quantity < 6 ? restock : sufficient,
);
console.log(result.get(restock));
// [{ name: "bananas", type: "fruit", quantity: 5 }]
```


Note that the function argument `{ quantity }` is a basic example of
[object destructuring syntax for function
arguments](../../operators/destructuring_assignment#unpacking_properties_from_objects_passed_as_a_function_parameter).
This unpacks the `quantity` property of an object passed as a parameter,
and assigns it to a variable named `quantity` in the body of the
function. This is a very succinct way to access the relevant values of
elements within a function.

The key to a `Map` can be modified and still used. However you can\'t
recreate the key and still use it. For this reason it is important that
anything that needs to use the map keeps a reference to its keys.

 
 
[js]


```js
// The key can be modified and still used
restock["fast"] = true;
console.log(result.get(restock));
// [{ name: "bananas", type: "fruit", quantity: 5 }]

// A new key can't be used, even if it has the same structure!
const restock2 = { restock: true };
console.log(result.get(restock2)); // undefined
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------
  [Array Grouping\
  [\#
  sec-map.groupby]](https://tc39.es/proposal-array-grouping/#sec-map.groupby)

  -------------------------------------------------------------------------------------


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

`groupBy`

117

117

119

103

16.4--previewpreview

117

119

78

16.4

No

117

1.37

21.0.0

 
See also 
--------

 
-   [Polyfill of `Map.groupBy` in
    `core-js`](https://github.com/zloirock/core-js#array-grouping)
-   [Indexed
    collections](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections)
    guide
-   [`Array.prototype.reduce()`](../array/reduce)
-   [`Map()`](map)
-   [`Object.groupBy()`](../object/groupby)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map/groupBy>

