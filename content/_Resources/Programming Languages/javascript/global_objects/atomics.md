Atomics
=======

 
The `Atomics` namespace object contains static methods for carrying out
atomic operations. They are used with
[`SharedArrayBuffer`](sharedarraybuffer) and
[`ArrayBuffer`](arraybuffer) objects.


 
Description
-----------

 
Unlike most global objects, `Atomics` is not a constructor. You cannot
use it with the [`new` operator](../operators/new) or invoke the
`Atomics` object as a function. All properties and methods of `Atomics`
are static (just like the [`Math`](math) object).



 
### Atomic operations 

 
When memory is shared, multiple threads can read and write the same data
in memory. Atomic operations make sure that predictable values are
written and read, that operations are finished before the next operation
starts and that operations are not interrupted.



 
### Wait and notify 

 
The `wait()` and `notify()` methods are modeled on Linux futexes (\"fast
user-space mutex\") and provide ways for waiting until a certain
condition becomes true and are typically used as blocking constructs.



 
Static properties 
-----------------

 

[`Atomics[@@toStringTag]`](#atomicstostringtag)

:   The initial value of the [`@@toStringTag`](symbol/tostringtag)
    property is the string `"Atomics"`. This property is used in
    [`Object.prototype.toString()`](object/tostring).



 
Static methods 
--------------

 

[`Atomics.add()`](atomics/add)

:   Adds the provided value to the existing value at the specified index
    of the array. Returns the old value at that index.

[`Atomics.and()`](atomics/and)

:   Computes a bitwise AND on the value at the specified index of the
    array with the provided value. Returns the old value at that index.

[`Atomics.compareExchange()`](atomics/compareexchange)

:   Stores a value at the specified index of the array, if it equals a
    value. Returns the old value.

[`Atomics.exchange()`](atomics/exchange)

:   Stores a value at the specified index of the array. Returns the old
    value.

[`Atomics.isLockFree()`](atomics/islockfree)

:   An optimization primitive that can be used to determine whether to
    use locks or atomic operations. Returns `true` if an atomic
    operation on arrays of the given element size will be implemented
    using a hardware atomic operation (as opposed to a lock). Experts
    only.

[`Atomics.load()`](atomics/load)

:   Returns the value at the specified index of the array.

[`Atomics.notify()`](atomics/notify)

:   Notifies agents that are waiting on the specified index of the
    array. Returns the number of agents that were notified.

[`Atomics.or()`](atomics/or)

:   Computes a bitwise OR on the value at the specified index of the
    array with the provided value. Returns the old value at that index.

[`Atomics.store()`](atomics/store)

:   Stores a value at the specified index of the array. Returns the
    value.

[`Atomics.sub()`](atomics/sub)

:   Subtracts a value at the specified index of the array. Returns the
    old value at that index.

[`Atomics.wait()`](atomics/wait)

:   Verifies that the specified index of the array still contains a
    value and sleeps awaiting or times out. Returns either `"ok"`,
    `"not-equal"`, or `"timed-out"`. If waiting is not allowed in the
    calling agent then it throws an exception. (Most browsers will not
    allow `wait()` on the browser\'s main thread.)

[`Atomics.waitAsync()`](atomics/waitasync)

:   Waits asynchronously (i.e. without blocking, unlike `Atomics.wait`)
    on a shared memory location and returns a [`Promise`](promise).

[`Atomics.xor()`](atomics/xor)

:   Computes a bitwise XOR on the value at the specified index of the
    array with the provided value. Returns the old value at that index.



 
Examples
--------


 
### Using Atomics 

 
 
 
[js]


```js
const sab = new SharedArrayBuffer(1024);
const ta = new Uint8Array(sab);

ta[0]; // 0
ta[0] = 5; // 5

Atomics.add(ta, 0, 12); // 5
Atomics.load(ta, 0); // 17

Atomics.and(ta, 0, 1); // 17
Atomics.load(ta, 0); // 1

Atomics.compareExchange(ta, 0, 5, 12); // 1
Atomics.load(ta, 0); // 1

Atomics.exchange(ta, 0, 12); // 1
Atomics.load(ta, 0); // 12

Atomics.isLockFree(1); // true
Atomics.isLockFree(2); // true
Atomics.isLockFree(3); // false
Atomics.isLockFree(4); // true

Atomics.or(ta, 0, 1); // 12
Atomics.load(ta, 0); // 13

Atomics.store(ta, 0, 12); // 12

Atomics.sub(ta, 0, 2); // 12
Atomics.load(ta, 0); // 10

Atomics.xor(ta, 0, 1); // 10
Atomics.load(ta, 0); // 11
```




 
### Waiting and notifying 

 
Given a shared `Int32Array`:

 
 
[js]


```js
const sab = new SharedArrayBuffer(1024);
const int32 = new Int32Array(sab);
```


A reading thread is sleeping and waiting on location 0 which is expected
to be 0. As long as that is true, it will not go on. However, once the
writing thread has stored a new value, it will be notified by the
writing thread and return the new value (123).

 
 
[js]


```js
Atomics.wait(int32, 0, 0);
console.log(int32[0]); // 123
```


A writing thread stores a new value and notifies the waiting thread once
it has written:

 
 
[js]


```js
console.log(int32[0]); // 0;
Atomics.store(int32, 0, 123);
Atomics.notify(int32, 0, 1);
```




Specifications
--------------

 
  ---------------------------------------------------------------------------------------------------------
  Specification
  ---------------------------------------------------------------------------------------------------------
  [ECMAScript Language Specification\
  [\#
  sec-atomics-object]](https://tc39.es/ecma262/multipage/structured-data.html#sec-atomics-object)

  ---------------------------------------------------------------------------------------------------------


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

`Atomic_operations_on_non_shared_buffers`

No

No

79

No

No

No

79

No

No

No

No

No

No

`Atomics`

68

79

78

55

15.2Before Safari 16.4, `Atomics` is gated behind COOP/COEP. For more
detail, read [Making your website \"cross-origin isolated\" using COOP
and COEP](https://web.dev/coop-coep/).

89

79

63

15.2Before Safari 16.4, `Atomics` is gated behind COOP/COEP. For more
detail, read [Making your website \"cross-origin isolated\" using COOP
and COEP](https://web.dev/coop-coep/).

15.0

89

1.0

8.10.0

`add`

68

79

78

55

15.2

89

79

63

15.2

15.0

89

1.0

8.10.0

`and`

68

79

78

55

15.2

89

79

63

15.2

15.0

89

1.0

8.10.0

`compareExchange`

68

79

78

55

15.2

89

79

63

15.2

15.0

89

1.0

8.10.0

`exchange`

68

79

78

55

15.2

89

79

63

15.2

15.0

89

1.0

8.10.0

`isLockFree`

68

79

78

55

15.2

89

79

63

15.2

15.0

89

1.0

8.10.0

`load`

68

79

78

55

15.2

89

79

63

15.2

15.0

89

1.0

8.10.0

`notify`

68

79

78

55

15.2

89

79

63

15.2

15.0

89

1.0

8.10.0

`or`

68

79

78

55

15.2

89

79

63

15.2

15.0

89

1.0

8.10.0

`store`

68

79

78

55

15.2

89

79

63

15.2

15.0

89

1.0

8.10.0

`sub`

68

79

78

55

15.2

89

79

63

15.2

15.0

89

1.0

8.10.0

`wait`

68

79

78

55

15.2

89

79

63

15.2

15.0

89

1.0

8.10.0

`waitAsync`

87

87

No

75

16.4

89

No

63

16.4

15.0

89

1.4

16.0.0

`xor`

68

79

78

55

15.2

89

79

63

15.2

15.0

89

1.0

8.10.0

 
See also 
--------

 
-   [`ArrayBuffer`](arraybuffer)
-   [JavaScript typed
    arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Typed_arrays)
    guide
-   [Web
    Workers](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API)
-   [Shared Memory -- a brief
    tutorial](https://github.com/tc39/proposal-ecmascript-sharedmem/blob/main/TUTORIAL.md)
    in the TC39 ecmascript-sharedmem proposal
-   [A Taste of JavaScript\'s New Parallel
    Primitives](https://hacks.mozilla.org/2016/05/a-taste-of-javascripts-new-parallel-primitives/)
    on hacks.mozilla.org (2016)



 
© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Atomics>

