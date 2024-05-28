[dart:core](../dart-core/dart-core-library){._links-link}

Error class
===========

Error objects thrown in the case of a program failure.

An `Error` object represents a program failure that the programmer
should have avoided.

Examples include calling a function with invalid arguments, or even with
the wrong number of arguments, or calling it at a time when it is not
allowed.

These are not errors that a caller should expect or catch - if they
occur, the program is erroneous, and terminating the program may be the
safest response.

When deciding that a function throws an error, the conditions where it
happens should be clearly described, and they should be detectable and
predictable, so the programmer using the function can avoid triggering
the error.

Such descriptions often uses words like \"must\" or \"must not\" to
describe the condition, and if you see words like that in a function\'s
documentation, then not satisfying the requirement is very likely to
cause an error to be thrown.

Example (from [String.contains](string/contains)):

``` {.language-plaintext data-language="dart"}
`startIndex` must not be negative or greater than `length`.
```

In this case, an error will be thrown if `startIndex` is negative or too
large.

If the conditions are not detectable before calling a function, the
called function should not throw an `Error`. It may still throw, but the
caller will have to catch the thrown value, effectively making it an
alternative result rather than an error. The thrown object can choose to
implement [Exception](exception-class) to document that it represents an
exceptional, but not erroneous, occurrence, but being an
[Exception](exception-class) has no other effect than documentation.

All non-`null` values can be thrown in Dart. Objects extending `Error`
are handled specially: The first time they are thrown, the stack trace
at the throw point is recorded and stored in the error object. It can be
retrieved using the [stackTrace](error/stacktrace) getter. An error
object that merely implements `Error`, and doesn\'t extend it, will not
store the stack trace automatically.

Error objects are also used for system wide failures like stack overflow
or an out-of-memory situation.

Since errors are not created to be caught, there is no need for
subclasses to distinguish the errors. Instead subclasses have been
created in order to make groups of related errors easy to create with
consistent error messages. For example, the
[String.contains](string/contains) method will use a
[RangeError](rangeerror-class) if its `startIndex` isn\'t in the range
`0..length`, which is easily created by
`RangeError.range(startIndex, 0, length)`.

Implementers

:   -   [AbstractClassInstantiationError](abstractclassinstantiationerror-class){.deprecated}
    -   [ArgumentError](argumenterror-class)
    -   [AssertionError](assertionerror-class)
    -   [AsyncError](../dart-async/asyncerror-class)
    -   [CastError](casterror-class){.deprecated}
    -   [ConcurrentModificationError](concurrentmodificationerror-class)
    -   [CyclicInitializationError](cyclicinitializationerror-class)
    -   [FallThroughError](fallthrougherror-class)
    -   [JsonUnsupportedObjectError](../dart-convert/jsonunsupportedobjecterror-class)
    -   [NoSuchMethodError](nosuchmethoderror-class)
    -   [NullThrownError](nullthrownerror-class)
    -   [OutOfMemoryError](outofmemoryerror-class)
    -   [RemoteError](../dart-isolate/remoteerror-class)
    -   [StackOverflowError](stackoverflowerror-class)
    -   [StateError](stateerror-class)
    -   [TypeError](typeerror-class)
    -   [UnimplementedError](unimplementederror-class)
    -   [UnsupportedError](unsupportederror-class)

Constructors
------------

[Error](error/error)()

Properties {#instance-properties}
----------

[hashCode](object/hashcode) → [int](int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[runtimeType](object/runtimetype) → [Type](type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

[stackTrace](error/stacktrace) → [StackTrace](stacktrace-class)?

::: {.features}
read-only
:::

The stack trace at the point where this error was first thrown.

Methods {#instance-methods}
-------

[noSuchMethod](object/nosuchmethod)([Invocation](invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](object/tostring)() → [String](string-class)

::: {.features}
inherited
:::

A string representation of this object.

Operators
---------

[operator ==](object/operator_equals)([Object](object-class) other) →
[bool](bool-class)

::: {.features}
inherited
:::

The equality operator.

Static Methods
--------------

[safeToString](error/safetostring)([Object](object-class)? object) →
[String](string-class)

Safely convert a value to a [String](string-class) description.

[throwWithStackTrace](error/throwwithstacktrace)([Object](object-class)
error, [StackTrace](stacktrace-class) stackTrace) → Never

::: {.features}
\@Since(\"2.16\")
:::

Throws `error` with associated stack trace `stackTrace`.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Error-class.html>
:::
