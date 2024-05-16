BigInt.prototype.valueOf()
==========================

Baseline [Widely available]
--------------------------------------


This feature is well established and works across many devices and
browser versions. It's been available across browsers since September
2020.

-   [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-evolution-on-mdn/)
-   [See full compatibility](#browser_compatibility)
-   [Report
    feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FJavaScript%2FReference%2FGlobal_Objects%2FBigInt%2FvalueOf&level=high)



The `valueOf()` method of [`BigInt`](../bigint) values returns the
wrapped primitive value of a [`BigInt`](../bigint) object.



Try it 
------






Syntax
------




[js]


```js
valueOf()
```





### Parameters


None.




### Return value 


A BigInt representing the primitive value of the specified
[`BigInt`](../bigint) object.




Examples
--------



### Using `valueOf` 




[js]


```js
typeof Object(1n); // object
typeof Object(1n).valueOf(); // bigint
```




Specifications
--------------


  -------------------------------------------------------------------------------------------------------------------------------
  Specification
  -------------------------------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-bigint.prototype.valueof]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-bigint.prototype.valueof)

  -------------------------------------------------------------------------------------------------------------------------------


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

`valueOf`

67

79

68

54

14

67

68

48

14

9.0

67

1.0

10.4.0


See also 
--------


-   [`BigInt.prototype.toString()`](tostring)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt/valueOf>

