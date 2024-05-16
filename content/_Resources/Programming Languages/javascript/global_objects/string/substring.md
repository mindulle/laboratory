String.prototype.substring()
============================

 
The `substring()` method of [`String`](../string) values returns the
part of this string from the start index up to and excluding the end
index, or to the end of the string if no end index is supplied.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
substring(indexStart)
substring(indexStart, indexEnd)
```




 
### Parameters

 

[`indexStart`](#indexstart)

:   The index of the first character to include in the returned
    substring.

[`indexEnd`](#indexend) [Optional]

:   The index of the first character to exclude from the returned
    substring.



 
### Return value 

 
A new string containing the specified part of the given string.



 
Description
-----------

 
`substring()` extracts characters from `indexStart` up to *but not
including* `indexEnd`. In particular:

-   If `indexEnd` is omitted, `substring()` extracts characters to the
    end of the string.
-   If `indexStart` is equal to `indexEnd`, `substring()` returns an
    empty string.
-   If `indexStart` is greater than `indexEnd`, then the effect of
    `substring()` is as if the two arguments were swapped; see example
    below.

Any argument value that is less than `0` or greater than `str.length` is
treated as if it were `0` and `str.length`, respectively.

Any argument value that is [`NaN`](../nan) is treated as if it were `0`.



 
Examples
--------


 
### Using substring() 

 
The following example uses `substring()` to display characters from the
string `"Mozilla"`:

 
 
[js]


```js
const anyString = "Mozilla";

console.log(anyString.substring(0, 1)); // "M"
console.log(anyString.substring(1, 0)); // "M"

console.log(anyString.substring(0, 6)); // "Mozill"

console.log(anyString.substring(4)); // "lla"
console.log(anyString.substring(4, 7)); // "lla"
console.log(anyString.substring(7, 4)); // "lla"

console.log(anyString.substring(0, 7)); // "Mozilla"
console.log(anyString.substring(0, 10)); // "Mozilla"
```




 
### Using substring() with length property 

 
The following example uses the `substring()` method and
[`length`](length) property to extract the last characters of a
particular string. This method may be easier to remember, given that you
don\'t need to know the starting and ending indices as you would in the
above examples.

 
 
[js]


```js
const text = "Mozilla";

// Takes 4 last characters of string
console.log(text.substring(text.length - 4)); // prints "illa"

// Takes 5 last characters of string
console.log(text.substring(text.length - 5)); // prints "zilla"
```




 
### The difference between substring() and substr() 

 
There are subtle differences between the `substring()` and
[`substr()`](substr) methods, so you should be careful not to get them
confused.

-   The two parameters of `substr()` are `start` and `length`, while for
    `substring()`, they are `start` and `end`.
-   `substr()`\'s `start` index will wrap to the end of the string if it
    is negative, while `substring()` will clamp it to `0`.
-   Negative lengths in `substr()` are treated as zero, while
    `substring()` will swap the two indexes if `end` is less than
    `start`.

Furthermore, `substr()` is considered a *legacy feature in ECMAScript*,
so it is best to avoid using it if possible.

 
 
[js]


```js
const text = "Mozilla";
console.log(text.substring(2, 5)); // "zil"
console.log(text.substr(2, 3)); // "zil"
```




 
### Differences between substring() and slice() 

 
The `substring()` and [`slice()`](slice) methods are almost identical,
but there are a couple of subtle differences between the two, especially
in the way negative arguments are dealt with.

The `substring()` method swaps its two arguments if `indexStart` is
greater than `indexEnd`, meaning that a string is still returned. The
[`slice()`](slice) method returns an empty string if this is the case.

 
 
[js]


```js
const text = "Mozilla";
console.log(text.substring(5, 2)); // "zil"
console.log(text.slice(5, 2)); // ""
```


If either or both of the arguments are negative or `NaN`, the
`substring()` method treats them as if they were `0`.

 
 
[js]


```js
console.log(text.substring(-5, 2)); // "Mo"
console.log(text.substring(-5, -2)); // ""
```


`slice()` also treats `NaN` arguments as `0`, but when it is given
negative values it counts backwards from the end of the string to find
the indexes.

 
 
[js]


```js
console.log(text.slice(-5, 2)); // ""
console.log(text.slice(-5, -2)); // "zil"
```


See the [`slice()`](slice) page for more examples with negative numbers.



 
### Replacing a substring within a string 

 
The following example replaces a substring within a string. It will
replace both individual characters and substrings. The function call at
the end of the example changes the string `Brave New World` to
`Brave New Web`.

 
 
[js]


```js
// Replaces oldS with newS in the string fullS
function replaceString(oldS, newS, fullS) {
  for (let i = 0; i < fullS.length; ++i) {
    if (fullS.substring(i, i + oldS.length) === oldS) {
      fullS =
        fullS.substring(0, i) +
        newS +
        fullS.substring(i + oldS.length, fullS.length);
    }
  }
  return fullS;
}

replaceString("World", "Web", "Brave New World");
```


Note that this can result in an infinite loop if `oldS` is itself a
substring of `newS` --- for example, if you attempted to replace
`"World"` with `"OtherWorld"` here.

A better method for replacing strings is as follows:

 
 
[js]


```js
function replaceString(oldS, newS, fullS) {
  return fullS.split(oldS).join(newS);
}
```


The code above serves as an example for substring operations. If you
need to replace substrings, most of the time you will want to use
[`String.prototype.replace()`](replace).



Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-string.prototype.substring]](https://tc39.es/ecma262/multipage/text-processing.html#sec-string.prototype.substring)

  ---------------------------------------------------------------------------------------------------------------------------------


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

`substring`

1

12

1

3

1

18

4

10.1

1

1.0

4.4

1.0

0.10.0

 
See also 
--------

 
-   [`String.prototype.substr()`](substr)
-   [`String.prototype.slice()`](slice)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/substring>

