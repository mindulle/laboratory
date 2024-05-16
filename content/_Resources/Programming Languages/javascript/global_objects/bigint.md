BigInt
======

Baseline [Widely available]
--------------------------------------

 
This feature is well established and works across many devices and
browser versions. It's been available across browsers since September
2020.

-   [Learn
    more](https://developer.mozilla.org/en-US/blog/baseline-evolution-on-mdn/)
-   [See full compatibility](#browser_compatibility)
-   [Report
    feedback](https://survey.alchemer.com/s3/7634825/MDN-baseline-feedback?page=%2Fen-US%2Fdocs%2FWeb%2FJavaScript%2FReference%2FGlobal_Objects%2FBigInt&level=high)


 
`BigInt` values represent numeric values which are [too
large](number/max_safe_integer) to be represented by the `number`
[primitive](https://developer.mozilla.org/en-US/docs/Glossary/Primitive).


 
Description
-----------

 
A **BigInt value**, also sometimes just called a **BigInt**, is a
`bigint`
[primitive](https://developer.mozilla.org/en-US/docs/Glossary/Primitive),
created by appending `n` to the end of an integer literal, or by calling
the [`BigInt()`](bigint/bigint) function (without the `new` operator)
and giving it an integer value or string value.

 
 
[js]


```js
const previouslyMaxSafeInteger = 9007199254740991n;

const alsoHuge = BigInt(9007199254740991);
// 9007199254740991n

const hugeString = BigInt("9007199254740991");
// 9007199254740991n

const hugeHex = BigInt("0x1fffffffffffff");
// 9007199254740991n

const hugeOctal = BigInt("0o377777777777777777");
// 9007199254740991n

const hugeBin = BigInt(
  "0b11111111111111111111111111111111111111111111111111111",
);
// 9007199254740991n
```


BigInt values are similar to Number values in some ways, but also differ
in a few key matters: A BigInt value cannot be used with methods in the
built-in [`Math`](math) object and cannot be mixed with a Number value
in operations; they must be coerced to the same type. Be careful
coercing values back and forth, however, as the precision of a BigInt
value may be lost when it is coerced to a Number value.



 
### Type information 


When tested against `typeof`, a BigInt value (`bigint` primitive) will
give `"bigint"`:



[js]


```js
typeof 1n === "bigint"; // true
typeof BigInt("1") === "bigint"; // true
```


A BigInt value can also be wrapped in an `Object`:



[js]


```js
typeof Object(1n) === "object"; // true
```





### Operators


Most operators support BigInts, however most do not permit operands to
be of mixed types --- both operands must be BigInt or neither:

-   [Arithmetic
    operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#arithmetic_operators):
    `+`, `-`, `*`, `/`, `%`, `**`
-   [Bitwise
    operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#bitwise_shift_operators):
    `>>`, `<<`, `&`, `|`, `^`, `~`
-   [Unary negation (`-`)](../operators/unary_negation)
-   [Increment/decrement](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#increment_and_decrement):
    `++`, `--`

The boolean-returning operators allow mixing numbers and BigInts as
operands:

-   [Relational
    operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#relational_operators)
    and [equality
    operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#equality_operators):
    `>`, `<`, `>=`, `<=`, `==`, `!=`, `===`, `!==`
-   [Logical
    operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#binary_logical_operators)
    only rely on the
    [truthiness](https://developer.mozilla.org/en-US/docs/Glossary/Truthy)
    of operands

A couple of operators do not support BigInt at all:

-   [Unary plus (`+`)](../operators/unary_plus) cannot be supported due
    to conflicting usage in asm.js, so it has been left out [in order to
    not break
    asm.js](https://github.com/tc39/proposal-bigint/blob/master/ADVANCED.md#dont-break-asmjs).
-   [Unsigned right shift (`>>>`)](../operators/unsigned_right_shift) is
    the only bitwise operator that\'s unsupported, as every BigInt value
    is signed.

Special cases:

-   Addition (`+`) involving a string and a BigInt returns a string.
-   Division (`/`) truncates fractional components towards zero, since
    BigInt is unable to represent fractional quantities.



[js]


```js
const previousMaxSafe = BigInt(Number.MAX_SAFE_INTEGER); // 9007199254740991n
const maxPlusOne = previousMaxSafe + 1n; // 9007199254740992n
const theFuture = previousMaxSafe + 2n; // 9007199254740993n, this works now!
const multi = previousMaxSafe * 2n; // 18014398509481982n
const subtr = multi - 10n; // 18014398509481972n
const mod = multi % 10n; // 2n
const bigN = 2n ** 54n; // 18014398509481984n
bigN * -1n; // -18014398509481984n
const expected = 4n / 2n; // 2n
const truncated = 5n / 2n; // 2n, not 2.5n
```





### Comparisons


A BigInt value is not strictly equal to a Number value, but it *is*
loosely so:



[js]


```js
0n === 0; // false
0n == 0; // true
```


A Number value and a BigInt value may be compared as usual:



[js]


```js
1n < 2; // true
2n > 1; // true
2 > 2; // false
2n > 2; // false
2n >= 2; // true
```


BigInt values and Number values may be mixed in arrays and sorted:



[js]


```js
const mixed = [4n, 6, -12n, 10, 4, 0, 0n];
// [4n, 6, -12n, 10, 4, 0, 0n]

mixed.sort(); // default sorting behavior
// [ -12n, 0, 0n, 10, 4n, 4, 6 ]

mixed.sort((a, b) => a - b);
// won't work since subtraction will not work with mixed types
// TypeError: can't convert BigInt value to Number value

// sort with an appropriate numeric comparator
mixed.sort((a, b) => (a < b ? -1 : a > b ? 1 : 0));
// [ -12n, 0, 0n, 4n, 4, 6, 10 ]
```


Note that comparisons with `Object`-wrapped BigInt values act as with
other objects, only indicating equality when the same object instance is
compared:



[js]


```js
Object(0n) === 0n; // false
Object(0n) === Object(0n); // false

const o = Object(0n);
o === o; // true
```


Because coercing between Number values and BigInt values can lead to
loss of precision, the following are recommended:

-   Only use a BigInt value when values greater than 2^53^ are
    reasonably expected.
-   Don\'t coerce between BigInt values and Number values.




### Conditionals


A BigInt value follows the same conversion rules as Numbers when:

-   it is converted to a [`Boolean`](boolean): via the
    [`Boolean`](boolean) function;
-   when used with [logical
    operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators)
    `||`, `&&`, and `!`; or
-   within a conditional test like an [`if`](../statements/if...else)
    statement.

Namely, only `0n` is
[falsy](https://developer.mozilla.org/en-US/docs/Glossary/Falsy);
everything else is
[truthy](https://developer.mozilla.org/en-US/docs/Glossary/Truthy).



[js]


```js
if (0n) {
  console.log("Hello from the if!");
} else {
  console.log("Hello from the else!");
}
// "Hello from the else!"

0n || 12n; // 12n
0n && 12n; // 0n
Boolean(0n); // false
Boolean(12n); // true
!12n; // false
!0n; // true
```





### Cryptography


The operations supported on BigInt values are not constant-time and are
thus open to [timing
attacks](https://en.wikipedia.org/wiki/Timing_attack). JavaScript
BigInts therefore could be dangerous for use in cryptography without
mitigating factors. As a very generic example, an attacker could measure
the time difference between `101n ** 65537n` and `17n ** 9999n`, and
deduce the magnitude of secrets, such as private keys, based on the time
elapsed. If you still have to use BigInts, take a look at the [Timing
attack FAQ](https://timing.attacks.cr.yp.to/programming.html) for
general advice regarding the issue.




### Use within JSON 


Using [`JSON.stringify()`](json/stringify) with any BigInt value will
raise a `TypeError`, as BigInt values aren\'t serialized in JSON by
default. However, `JSON.stringify()` specifically leaves a backdoor for
BigInt values: it would try to call the BigInt\'s `toJSON()` method. (It
doesn\'t do so for any other primitive values.) Therefore, you can
implement your own `toJSON()` method (which is one of the few cases
where patching built-in objects is not explicitly discouraged):



[js]


```js
BigInt.prototype.toJSON = function () {
  return this.toString();
};
```


Instead of throwing, `JSON.stringify()` now produces a string like this:



[js]


```js
console.log(JSON.stringify({ a: 1n }));
// {"a":"1"}
```


If you do not wish to patch `BigInt.prototype`, you can use the
[`replacer`](json/stringify#the_replacer_parameter) parameter of
`JSON.stringify` to serialize BigInt values:



[js]


```js
const replacer = (key, value) =>
  typeof value === "bigint" ? value.toString() : value;

const data = {
  number: 1,
  big: 18014398509481982n,
};
const stringified = JSON.stringify(data, replacer);

console.log(stringified);
// {"number":1,"big":"18014398509481982"}
```


If you have JSON data containing values you know will be large integers,
you can use the [`reviver`](json/parse#using_the_reviver_parameter)
parameter of `JSON.parse` to handle them:



[js]


```js
const reviver = (key, value) => (key === "big" ? BigInt(value) : value);

const payload = '{"number":1,"big":"18014398509481982"}';
const parsed = JSON.parse(payload, reviver);

console.log(parsed);
// { number: 1, big: 18014398509481982n }
```


 
**Note:** While it\'s possible to make the replacer of
`JSON.stringify()` generic and properly serialize BigInt values for all
objects, the reviver of `JSON.parse()` must be specific to the payload
shape you expect, because the serialization is *lossy*: it\'s not
possible to distinguish between a string that represents a BigInt and a
normal string.





### BigInt coercion 


Many built-in operations that expect BigInts first coerce their
arguments to BigInts. [The
operation](https://tc39.es/ecma262/multipage/abstract-operations.html#sec-tobigint)
can be summarized as follows:

-   BigInts are returned as-is.
-   [`undefined`](undefined) and [`null`](../operators/null) throw a
    [`TypeError`](typeerror).
-   `true` turns into `1n`; `false` turns into `0n`.
-   Strings are converted by parsing them as if they contain an integer
    literal. Any parsing failure results in a
    [`SyntaxError`](syntaxerror). The syntax is a subset of [string
    numeric literals](number#number_coercion), where decimal points or
    exponent indicators are not allowed.
-   [Numbers](number) throw a [`TypeError`](typeerror) to prevent
    unintended implicit coercion causing loss of precision.
-   [Symbols](symbol) throw a [`TypeError`](typeerror).
-   Objects are first [converted to a
    primitive](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#primitive_coercion)
    by calling their [`[@@toPrimitive]()`](symbol/toprimitive) (with
    `"number"` as hint), `valueOf()`, and `toString()` methods, in that
    order. The resulting primitive is then converted to a BigInt.

The best way to achieve nearly the same effect in JavaScript is through
the [`BigInt()`](bigint/bigint) function: `BigInt(x)` uses the same
algorithm to convert `x`, except that [Numbers](number) don\'t throw a
[`TypeError`](typeerror), but are converted to BigInts if they are
integers.

Note that built-in operations expecting BigInts often truncate the
BigInt to a fixed width after coercion. This includes
[`BigInt.asIntN()`](bigint/asintn),
[`BigInt.asUintN()`](bigint/asuintn), and methods of
[`BigInt64Array`](bigint64array) and [`BigUint64Array`](biguint64array).




Constructor
-----------



[`BigInt()`](bigint/bigint)

:   Creates a new BigInt value.




Static methods 
--------------



[`BigInt.asIntN()`](bigint/asintn)

:   Clamps a BigInt value to a signed integer value, and returns that
    value.

[`BigInt.asUintN()`](bigint/asuintn)

:   Clamps a BigInt value to an unsigned integer value, and returns that
    value.




Instance properties 
-------------------


These properties are defined on `BigInt.prototype` and shared by all
`BigInt` instances.

[`BigInt.prototype.constructor`](object/constructor)

:   The constructor function that created the instance object. For
    `BigInt` instances, the initial value is the
    [`BigInt`](bigint/bigint) constructor.

[`BigInt.prototype[@@toStringTag]`](#bigint.prototypetostringtag)

:   The initial value of the [`@@toStringTag`](symbol/tostringtag)
    property is the string `"BigInt"`. This property is used in
    [`Object.prototype.toString()`](object/tostring). However, because
    `BigInt` also has its own [`toString()`](bigint/tostring) method,
    this property is not used unless you call
    [`Object.prototype.toString.call()`](function/call) with a BigInt as
    `thisArg`.




Instance methods 
----------------



[`BigInt.prototype.toLocaleString()`](bigint/tolocalestring)

:   Returns a string with a language-sensitive representation of this
    BigInt value. Overrides the
    [`Object.prototype.toLocaleString()`](object/tolocalestring) method.

[`BigInt.prototype.toString()`](bigint/tostring)

:   Returns a string representing this BigInt value in the specified
    radix (base). Overrides the
    [`Object.prototype.toString()`](object/tostring) method.

[`BigInt.prototype.valueOf()`](bigint/valueof)

:   Returns this BigInt value. Overrides the
    [`Object.prototype.valueOf()`](object/valueof) method.




Examples
--------



### Calculating Primes 




[js]


```js
// Returns true if the passed BigInt value is a prime number
function isPrime(p) {
  for (let i = 2n; i * i <= p; i++) {
    if (p % i === 0n) return false;
  }
  return true;
}

// Takes a BigInt value as an argument, returns nth prime number as a BigInt value
function nthPrime(nth) {
  let maybePrime = 2n;
  let prime = 0n;

  while (nth >= 0n) {
    if (isPrime(maybePrime)) {
      nth--;
      prime = maybePrime;
    }
    maybePrime++;
  }

  return prime;
}

nthPrime(20n);
// 73n
```




Specifications
--------------


  -----------------------------------------------------------------------------------------------------------
  Specification
  -----------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-bigint-objects]](https://tc39.es/ecma262/multipage/numbers-and-dates.html#sec-bigint-objects)

  -----------------------------------------------------------------------------------------------------------


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

`BigInt`

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

`BigInt`

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

`asIntN`

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

`asUintN`

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

`toLocaleString`

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

`toString`

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


-   [`Number`](number)
-   [`Number.MAX_SAFE_INTEGER`](number/max_safe_integer)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/BigInt>

