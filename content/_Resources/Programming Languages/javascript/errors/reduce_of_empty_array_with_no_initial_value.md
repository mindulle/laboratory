TypeError: Reduce of empty array with no initial value
======================================================

 
The JavaScript exception \"reduce of empty array with no initial value\"
occurs when a reduce function is used.


 
Message
-------

 
```text
TypeError: Reduce of empty array with no initial value (V8-based & Firefox & Safari)
```



 
Error type 
----------

 
[`TypeError`](../global_objects/typeerror)



 
What went wrong? 
----------------

 
In JavaScript, there are several reduce functions:

-   [`Array.prototype.reduce()`](../global_objects/array/reduce),
    [`Array.prototype.reduceRight()`](../global_objects/array/reduceright)
    and
-   [`TypedArray.prototype.reduce()`](../global_objects/typedarray/reduce),
    [`TypedArray.prototype.reduceRight()`](../global_objects/typedarray/reduceright)).

These functions optionally take an `initialValue` (which will be used as
the first argument to the first call of the `callback`). However, if no
initial value is provided, it will use the first element of the
[`Array`](../global_objects/array) or
[`TypedArray`](../global_objects/typedarray) as the initial value. This
error is raised when an empty array is provided because no initial value
can be returned in that case.



 
Examples
--------


 
### Invalid cases 

 
This problem appears frequently when combined with a filter
([`Array.prototype.filter()`](../global_objects/array/filter),
[`TypedArray.prototype.filter()`](../global_objects/typedarray/filter))
which will remove all elements of the list. Thus leaving none to be used
as the initial value.

 
 
[js]


```js
const ints = [0, -1, -2, -3, -4, -5];
ints
  .filter((x) => x > 0) // removes all elements
  .reduce((x, y) => x + y); // no more elements to use for the initial value.
```


Similarly, the same issue can happen if there is a typo in a selector,
or an unexpected number of elements in a list:

 
 
[js]


```js
const names = document.getElementsByClassName("names");
const name_list = Array.prototype.reduce.call(
  names,
  (acc, name) => acc + ", " + name,
);
```




 
### Valid cases 

 
These problems can be solved in two different ways.

One way is to actually provide an `initialValue` as the neutral element
of the operator, such as 0 for the addition, 1 for a multiplication, or
an empty string for a concatenation.

 
 
[js]


```js
const ints = [0, -1, -2, -3, -4, -5];
ints
  .filter((x) => x > 0) // removes all elements
  .reduce((x, y) => x + y, 0); // the initial value is the neutral element of the addition
```


Another way would be to handle the empty case, either before calling
`reduce`, or in the callback after adding an unexpected dummy initial
value.

 
 
[js]


```js
const names = document.getElementsByClassName("names");

let nameList1 = "";
if (names.length >= 1) {
  nameList1 = Array.prototype.reduce.call(
    names,
    (acc, name) => `${acc}, ${name}`,
  );
}
// nameList1 === "" when names is empty.

const nameList2 = Array.prototype.reduce.call(
  names,
  (acc, name) => {
    if (acc === "")
      // initial value
      return name;
    return `${acc}, ${name}`;
  },
  "",
);
// nameList2 === "" when names is empty.
```




 
See also 
--------

 
-   [`Array.prototype.reduce()`](../global_objects/array/reduce)
-   [`Array.prototype.reduceRight()`](../global_objects/array/reduceright)
-   [`TypedArray.prototype.reduce()`](../global_objects/typedarray/reduce)
-   [`TypedArray.prototype.reduceRight()`](../global_objects/typedarray/reduceright)
-   [`Array`](../global_objects/array)
-   [`TypedArray`](../global_objects/typedarray)
-   [`Array.prototype.filter()`](../global_objects/array/filter)
-   [`TypedArray.prototype.filter()`](../global_objects/typedarray/filter)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Reduce_of_empty_array_with_no_initial_value>

