Date.prototype.toJSON()
=======================

 
The `toJSON()` method of [`Date`](../date) instances returns a string
representing this date in the same ISO format as
[`toISOString()`](toisostring).


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
toJSON()
```




 
### Parameters

 
None.



 
### Return value 

 
A string representing the given date in the [date time string
format](../date#date_time_string_format) according to universal time, or
`null` when the date is
[invalid](../date#the_epoch_timestamps_and_invalid_date). For valid
dates, the return value is the same as that of
[`toISOString()`](toisostring).



 
Description
-----------

 
The `toJSON()` method is automatically called by
[`JSON.stringify()`](../json/stringify) when a `Date` object is
stringified. This method is generally intended to, by default, usefully
serialize [`Date`](../date) objects during
[JSON](https://developer.mozilla.org/en-US/docs/Glossary/JSON)
serialization, which can then be deserialized using the [`Date()`](date)
constructor as the reviver of [`JSON.parse()`](../json/parse).

The method first attempts to convert its `this` value [to a
primitive](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#primitive_coercion)
by calling its [`[@@toPrimitive]()`](../symbol/toprimitive) (with
`"number"` as hint), [`valueOf()`](../object/valueof), and
[`toString()`](../object/tostring) methods, in that order. If the result
is a [non-finite](../number/isfinite) number, `null` is returned. (This
generally corresponds to an invalid date, whose [`valueOf()`](valueof)
returns [`NaN`](../nan).) Otherwise, if the converted primitive is not a
number or is a finite number, the return value of
[`this.toISOString()`](toisostring) is returned.

Note that the method does not check whether the `this` value is a valid
[`Date`](../date) object. However, calling `Date.prototype.toJSON()` on
non-`Date` objects fails unless the object\'s number primitive
representation is `NaN`, or the object also has a `toISOString()`
method.



 
Examples
--------


 
### Using toJSON() 

 
 
 
[js]


```js
const jsonDate = new Date(0).toJSON(); // '1970-01-01T00:00:00.000Z'
const backToDate = new Date(jsonDate);

console.log(jsonDate); // 1970-01-01T00:00:00.000Z
```




 
### Serialization round-tripping 

 
When parsing JSON containing date strings, you can use the
[`Date()`](date) constructor to revive them into the original date
objects.

 
 
[js]


```js
const fileData = {
  author: "Maria",
  title: "Date.prototype.toJSON()",
  createdAt: new Date(2019, 3, 15),
  updatedAt: new Date(2020, 6, 26),
};
const response = JSON.stringify(fileData);

// Imagine transmission through network

const data = JSON.parse(response, (key, value) => {
  if (key === "createdAt" || key === "updatedAt") {
    return new Date(value);
  }
  return value;
});

console.log(data);
```


 
**Note:** The reviver of `JSON.parse()` must be specific to the payload
shape you expect, because the serialization is *lossy*: it\'s not
possible to distinguish between a string that represents a Date and a
normal string.




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-date.prototype.tojson]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-date.prototype.tojson)

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

`toJSON`

3

12

1

10.5

4

18

4

11

3.2

1.0

≤37

1.0

0.10.0

 
See also 
--------

 
-   [`Date.prototype.toLocaleDateString()`](tolocaledatestring)
-   [`Date.prototype.toTimeString()`](totimestring)
-   [`Date.prototype.toUTCString()`](toutcstring)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date/toJSON>

