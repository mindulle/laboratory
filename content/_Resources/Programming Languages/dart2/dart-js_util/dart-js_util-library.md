dart:js\_util library
=====================

Utility methods to manipulate `package:js` annotated JavaScript interop
objects in cases where the name to call is not known at runtime.

You should only use these methods when the same effect cannot be
achieved with `@JS()` annotations.

Properties
----------

[globalThis](globalthis) → [Object](../dart-core/object-class)

::: {.features}
read-only
:::

[objectPrototype](objectprototype) →
[Object](../dart-core/object-class)?

::: {.features}
read-only
:::

Returns the `Object` prototype. Equivalent to `Object.prototype`.

Functions
---------

[add](add)\<T\>([Object](../dart-core/object-class)? first, [Object](../dart-core/object-class)? second) → T
:   Perform JavaScript addition (`+`) on two values.

[callConstructor](callconstructor)\<T\>([Object](../dart-core/object-class) constr, [List](../dart-core/list-class)\<[Object](../dart-core/object-class)?\>? arguments) → T\
[callMethod](callmethod)\<T\>([Object](../dart-core/object-class) o, [String](../dart-core/string-class) method, [List](../dart-core/list-class)\<[Object](../dart-core/object-class)?\> args) → T\
[dartify](dartify)([Object](../dart-core/object-class)? o) → [Object](../dart-core/object-class)?
:   Effectively the inverse of [jsify](jsify), [dartify](dartify) Takes
    a JavaScript object, and converts it to a Dart based object. Only JS
    primitives, arrays, or \'map\' like JS objects are supported.

[divide](divide)\<T\>([Object](../dart-core/object-class)? first, [Object](../dart-core/object-class)? second) → T
:   Perform JavaScript division (`/`) on two values.

[equal](equal)\<T\>([Object](../dart-core/object-class)? first, [Object](../dart-core/object-class)? second) → [bool](../dart-core/bool-class)
:   Perform JavaScript equality comparison (`==`) on two values.

[exponentiate](exponentiate)\<T\>([Object](../dart-core/object-class)? first, [Object](../dart-core/object-class)? second) → T
:   Perform JavaScript exponentiation (`**`) on two values.

[getProperty](getproperty)\<T\>([Object](../dart-core/object-class) o, [Object](../dart-core/object-class) name) → T\
[greaterThan](greaterthan)\<T\>([Object](../dart-core/object-class)? first, [Object](../dart-core/object-class)? second) → [bool](../dart-core/bool-class)
:   Perform JavaScript greater than comparison (`>`) of two values.

[greaterThanOrEqual](greaterthanorequal)\<T\>([Object](../dart-core/object-class)? first, [Object](../dart-core/object-class)? second) → [bool](../dart-core/bool-class)
:   Perform JavaScript greater than or equal comparison (`>=`) of two
    values.

[hasProperty](hasproperty)([Object](../dart-core/object-class) o, [Object](../dart-core/object-class) name) → [bool](../dart-core/bool-class)\
[instanceof](instanceof)([Object](../dart-core/object-class)? o, [Object](../dart-core/object-class) type) → [bool](../dart-core/bool-class)
:   Check whether `o` is an instance of `type`.

[instanceOfString](instanceofstring)([Object](../dart-core/object-class)? element, [String](../dart-core/string-class) objectType) → [bool](../dart-core/bool-class)
:   Like [instanceof](instanceof) only takes a
    [String](../dart-core/string-class) for the object name instead of a
    constructor object.

[isJavaScriptArray](isjavascriptarray)(dynamic value) → [bool](../dart-core/bool-class)
:   Returns `true` if a given object is a JavaScript array.

[isJavaScriptSimpleObject](isjavascriptsimpleobject)(dynamic value) → [bool](../dart-core/bool-class)
:   Returns `true` if a given object is a simple JavaScript object.

[jsify](jsify)([Object](../dart-core/object-class) object) → dynamic
:   Recursively converts a JSON-like collection to JavaScript compatible
    representation.

[lessThan](lessthan)\<T\>([Object](../dart-core/object-class)? first, [Object](../dart-core/object-class)? second) → [bool](../dart-core/bool-class)
:   Perform JavaScript less than comparison (`<`) of two values.

[lessThanOrEqual](lessthanorequal)\<T\>([Object](../dart-core/object-class)? first, [Object](../dart-core/object-class)? second) → [bool](../dart-core/bool-class)
:   Perform JavaScript less than or equal comparison (`<=`) of two
    values.

[modulo](modulo)\<T\>([Object](../dart-core/object-class)? first, [Object](../dart-core/object-class)? second) → T
:   Perform JavaScript remainder (`%`) on two values.

[multiply](multiply)\<T\>([Object](../dart-core/object-class)? first, [Object](../dart-core/object-class)? second) → T
:   Perform JavaScript multiplication (`*`) on two values.

[newObject](newobject)\<T\>() → T\
[notEqual](notequal)\<T\>([Object](../dart-core/object-class)? first, [Object](../dart-core/object-class)? second) → [bool](../dart-core/bool-class)
:   Perform JavaScript inequality comparison (`!=`) on two values.

[objectGetPrototypeOf](objectgetprototypeof)([Object](../dart-core/object-class)? object) → [Object](../dart-core/object-class)?
:   Returns the prototype of a given object. Equivalent to
    `Object.getPrototypeOf`.

[objectKeys](objectkeys)([Object](../dart-core/object-class)? object) → [List](../dart-core/list-class)\<[Object](../dart-core/object-class)?\>
:   Returns the keys for a given object. Equivalent to
    `Object.keys(object)`.

[promiseToFuture](promisetofuture)\<T\>([Object](../dart-core/object-class) jsPromise) → [Future](../dart-async/future-class)\<T\>
:   Converts a JavaScript Promise to a Dart
    [Future](../dart-async/future-class).

[setProperty](setproperty)\<T\>([Object](../dart-core/object-class) o, [Object](../dart-core/object-class) name, T? value) → T\
[strictEqual](strictequal)\<T\>([Object](../dart-core/object-class)? first, [Object](../dart-core/object-class)? second) → [bool](../dart-core/bool-class)
:   Perform JavaScript strict equality comparison (`===`) on two values.

[strictNotEqual](strictnotequal)\<T\>([Object](../dart-core/object-class)? first, [Object](../dart-core/object-class)? second) → [bool](../dart-core/bool-class)
:   Perform JavaScript strict inequality comparison (`!==`) on two
    values.

[subtract](subtract)\<T\>([Object](../dart-core/object-class)? first, [Object](../dart-core/object-class)? second) → T
:   Perform JavaScript subtraction (`-`) on two values.

Exceptions / Errors {#exceptions}
-------------------

[NullRejectionException](nullrejectionexception-class)
:   Exception for when the promise is rejected with a `null` or
    `undefined` value.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-js_util/dart-js_util-library.html>
:::
