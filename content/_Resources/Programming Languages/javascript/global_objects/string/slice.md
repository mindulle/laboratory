String.prototype.slice()
========================

 
The `slice()` method of [`String`](../string) values extracts a section
of this string and returns it as a new string, without modifying the
original string.


 
Try it 
------

 



 
Syntax
------

 
 
 
[js]


```js
slice(indexStart)
slice(indexStart, indexEnd)
```




 
### Parameters

 

[`indexStart`](#indexstart)

:   The index of the first character to include in the returned
    substring.

[`indexEnd`](#indexend) [Optional]

:   The index of the first character to exclude from the returned
    substring.



 
### Return value 

 
A new string containing the extracted section of the string.



 
Description
-----------

 
`slice()` extracts the text from one string and returns a new string.
Changes to the text in one string do not affect the other string.

`slice()` extracts up to but not including `indexEnd`. For example,
`str.slice(4, 8)` extracts the fifth character through the eighth
character (characters indexed `4`, `5`, `6`, and `7`):

```text
              indexStart        indexEnd
                  ↓               ↓
| 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 |
| T | h | e |   | m | i | r | r | o | r |

                  m   i   r   r
                 _______________
                      ↑
                    Result
```

-   If `indexStart >= str.length`, an empty string is returned.
-   If `indexStart < 0`, the index is counted from the end of the
    string. More formally, in this case, the substring starts at
    `max(indexStart + str.length, 0)`.
-   If `indexStart` is omitted, undefined, or cannot be [converted to a
    number](../number#number_coercion), it\'s treated as `0`.
-   If `indexEnd` is omitted, undefined, or cannot be [converted to a
    number](../number#number_coercion), or if `indexEnd >= str.length`,
    `slice()` extracts to the end of the string.
-   If `indexEnd < 0`, the index is counted from the end of the string.
    More formally, in this case, the substring ends at
    `max(indexEnd + str.length, 0)`.
-   If `indexEnd <= indexStart` after normalizing negative values (i.e.
    `indexEnd` represents a character that\'s before `indexStart`), an
    empty string is returned.



 
Examples
--------


 
### Using slice() to create a new string 

 
The following example uses `slice()` to create a new string.

 
 
[js]


```js
const str1 = "The morning is upon us."; // The length of str1 is 23.
const str2 = str1.slice(1, 8);
const str3 = str1.slice(4, -2);
const str4 = str1.slice(12);
const str5 = str1.slice(30);
console.log(str2); // he morn
console.log(str3); // morning is upon u
console.log(str4); // is upon us.
console.log(str5); // ""
```




 
### Using slice() with negative indexes 

 
The following example uses `slice()` with negative indexes.

 
 
[js]


```js
const str = "The morning is upon us.";
str.slice(-3); // 'us.'
str.slice(-3, -1); // 'us'
str.slice(0, -1); // 'The morning is upon us'
str.slice(4, -1); // 'morning is upon us'
```


This example counts backwards from the end of the string by `11` to find
the start index and forwards from the start of the string by `16` to
find the end index.

 
 
[js]


```js
console.log(str.slice(-11, 16)); // "is u"
```


Here it counts forwards from the start by `11` to find the start index
and backwards from the end by `7` to find the end index.

 
 
[js]


```js
console.log(str.slice(11, -7)); // " is u"
```


These arguments count backwards from the end by `5` to find the start
index and backwards from the end by `1` to find the end index.

 
 
[js]


```js
console.log(str.slice(-5, -1)); // "n us"
```




Specifications
--------------

 
  -------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-string.prototype.slice]](https://tc39.es/ecma262/multipage/text-processing.html#sec-string.prototype.slice)

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

`slice`

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

 
See also 
--------

 
-   [`String.prototype.substr()`](substr)
-   [`String.prototype.substring()`](substring)
-   [`Array.prototype.slice()`](../array/slice)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/slice>

