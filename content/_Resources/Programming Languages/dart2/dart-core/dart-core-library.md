dart:core library
=================

Built-in types, collections, and other core functionality for every Dart
program.

This library is automatically imported.

Some classes in this library, such as [String](string-class) and
[num](num-class), support Dart\'s built-in data types. Other classes,
such as [List](list-class) and [Map](map-class), provide data structures
for managing collections of objects. And still other classes represent
commonly used types of data such as URIs, dates and times, and errors.

Numbers and booleans
--------------------

[int](int-class) and [double](double-class) provide support for Dart\'s
built-in numerical data types: integers and double-precision floating
point numbers, respectively. An object of type [bool](bool-class) is
either true or false. Variables of these types can be constructed from
literals:

``` {.language-dart data-language="dart"}
int meaningOfLife = 42;
double valueOfPi  = 3.141592;
bool visible      = true;
```

Strings and regular expressions
-------------------------------

A [String](string-class) is immutable and represents a sequence of
characters.

``` {.language-dart data-language="dart"}
String shakespeareQuote = "All the world's a stage, ...";
```

[StringBuffer](stringbuffer-class) provides a way to construct strings
efficiently.

``` {.language-dart data-language="dart"}
var moreShakespeare = StringBuffer();
moreShakespeare.write('And all the men and women ');
moreShakespeare.write('merely players; ...');
```

The [String](string-class) and [StringBuffer](stringbuffer-class)
classes implement string splitting, concatenation, and other string
manipulation features.

``` {.language-dart data-language="dart"}
bool isPalindrome(String text) => text == text.split('').reversed.join();
```

[RegExp](regexp-class) implements Dart regular expressions, which
provide a grammar for matching patterns within text. For example,
here\'s a regular expression that matches a substring containing one or
more digits:

``` {.language-dart data-language="dart"}
var numbers = RegExp(r'\d+');
```

Dart regular expressions have the same syntax and semantics as
JavaScript regular expressions. See
[ecma-international.org/ecma-262/5.1/\#sec-15.10](http://ecma-international.org/ecma-262/5.1/#sec-15.10)
for the specification of JavaScript regular expressions.

Collections
-----------

The `dart:core` library provides basic collections, such as
[List](list-class), [Map](map-class), and [Set](set-class).

A [List](list-class) is an ordered collection of objects, with a length.
Lists are sometimes called arrays. Use a [List](list-class) when you
need to access objects by index.

``` {.language-dart data-language="dart"}
var superheroes = ['Batman', 'Superman', 'Harry Potter'];
```

A [Set](set-class) is an unordered collection of unique objects. You
cannot get an item efficiently by index (position). Adding an element
which is already in the set, has no effect.

``` {.language-dart data-language="dart"}
var villains = {'Joker'};
print(villains.length); // 1
villains.addAll(['Joker', 'Lex Luthor', 'Voldemort']);
print(villains.length); // 3
```

A [Map](map-class) is an unordered collection of key-value pairs, where
each key can only occur once. Maps are sometimes called associative
arrays because maps associate a key to some value for easy retrieval.
Use a [Map](map-class) when you need to access objects by a unique
identifier.

``` {.language-dart data-language="dart"}
var sidekicks = {'Batman': 'Robin',
                 'Superman': 'Lois Lane',
                 'Harry Potter': 'Ron and Hermione'};
```

In addition to these classes, `dart:core` contains
[Iterable](iterable-class), an interface that defines functionality
common in collections of objects. Examples include the ability to run a
function on each element in the collection, to apply a test to each
element, to retrieve an object, and to determine the number of elements.

[Iterable](iterable-class) is implemented by [List](list-class) and
[Set](set-class), and used by [Map](map-class) for its keys and values.

For other kinds of collections, check out the `dart:collection` library.

Date and time
-------------

Use [DateTime](datetime-class) to represent a point in time and
[Duration](duration-class) to represent a span of time.

You can create [DateTime](datetime-class) objects with constructors or
by parsing a correctly formatted string.

``` {.language-dart data-language="dart"}
var now = DateTime.now();
var berlinWallFell = DateTime(1989, 11, 9);
var moonLanding = DateTime.parse("1969-07-20");
```

Create a [Duration](duration-class) object by specifying the individual
time units.

``` {.language-dart data-language="dart"}
var timeRemaining = const Duration(hours: 56, minutes: 14);
```

In addition to [DateTime](datetime-class) and
[Duration](duration-class), `dart:core` contains the
[Stopwatch](stopwatch-class) class for measuring elapsed time.

Uri
---

A [Uri](uri-class) object represents a uniform resource identifier,
which identifies a resource, for example on the web.

``` {.language-dart data-language="dart"}
var dartlang = Uri.parse('http://dartlang.org/');
```

Errors
------

The [Error](error-class) class represents the occurrence of an error
during runtime. Subclasses of this class represent specific kinds of
errors.

Other documentation
-------------------

For more information about how to use the built-in types, refer to
[Built-in
Types](https://dart.dev/guides/language/language-tour#built-in-types) in
[A tour of the Dart
language](https://dart.dev/guides/language/language-tour).

Also, see [dart:core - numbers, collections, strings, and
more](https://dart.dev/guides/libraries/library-tour#dartcore---numbers-collections-strings-and-more)
for more coverage of types in this library.

The [Dart Language Specification](https://dart.dev/guides/language/spec)
provides technical details.

Classes
-------

[BidirectionalIterator](bidirectionaliterator-class){.deprecated}\<E\>
:   An [Iterator](iterator-class) that allows moving backwards as well
    as forwards.

[BigInt](bigint-class)
:   An arbitrarily large integer value.

[bool](bool-class)
:   The reserved words `true` and `false` denote objects that are the
    only two instances of this class.

[Comparable](comparable-class)\<T\>
:   Interface used by types that have an intrinsic ordering.

[DateTime](datetime-class)
:   An instant in time, such as July 20, 1969, 8:18pm GMT.

[Deprecated](deprecated-class)
:   The annotation `@Deprecated('migration')` marks a feature as
    deprecated.

[double](double-class)
:   A double-precision floating point number.

[Duration](duration-class)
:   A span of time, such as 27 days, 4 hours, 12 minutes, and 3 seconds.

[Enum](enum-class)
:   An enumerated value.

[Expando](expando-class)\<T extends [Object](object-class)\>
:   An [Expando](expando-class) allows adding new properties to objects.

[Finalizer](finalizer-class)\<T\>
:   A finalizer which can be attached to Dart objects.

[Function](function-class)
:   The base class for all function types.

[Future](../dart-async/future-class)\<T\>
:   The result of an asynchronous computation.

[int](int-class)
:   An integer number.

[Invocation](invocation-class)
:   Representation of the invocation of a member on an object.

[Iterable](iterable-class)\<E\>
:   A collection of values, or \"elements\", that can be accessed
    sequentially.

[Iterator](iterator-class)\<E\>
:   An interface for getting items, one at a time, from an object.

[List](list-class)\<E\>
:   An indexable collection of objects with a length.

[Map](map-class)\<K, V\>
:   A collection of key/value pairs, from which you retrieve a value
    using its associated key.

[MapEntry](mapentry-class)\<K, V\>
:   A key/value pair representing an entry in a [Map](map-class).

[Match](match-class)
:   A result from searching within a string.

[Null](null-class)
:   The reserved word `null` denotes an object that is the sole instance
    of this class.

[num](num-class)
:   An integer or floating-point number.

[Object](object-class)
:   The base class for all Dart objects except `null`.

[Pattern](pattern-class)
:   An interface for basic searches within strings.

[pragma](pragma-class)
:   A hint to tools.

[Provisional](provisional-class){.deprecated}
:   An annotation class that was used during development of Dart 2.

[RegExp](regexp-class)
:   A regular expression pattern.

[RegExpMatch](regexpmatch-class)
:   A regular expression match.

[RuneIterator](runeiterator-class)
:   [Iterator](iterator-class) for reading runes (integer Unicode code
    points) of a Dart string.

[Runes](runes-class)
:   The runes (integer Unicode code points) of a [String](string-class).

[Set](set-class)\<E\>
:   A collection of objects in which each object can occur only once.

[Sink](sink-class)\<T\>
:   A generic destination for data.

[StackTrace](stacktrace-class)
:   An interface implemented by all stack trace objects.

[Stopwatch](stopwatch-class)
:   A stopwatch which measures time while it\'s running.

[Stream](../dart-async/stream-class)\<T\>
:   A source of asynchronous data events.

[String](string-class)
:   A sequence of UTF-16 code units.

[StringBuffer](stringbuffer-class)
:   A class for concatenating strings efficiently.

[StringSink](stringsink-class)\
[Symbol](symbol-class)
:   Opaque name used by mirrors, invocations and
    [Function.apply](function/apply).

[Type](type-class)
:   Runtime representation of a type.

[Uri](uri-class)
:   A parsed URI, such as a URL.

[UriData](uridata-class)
:   A way to access the structure of a `data:` URI.

[WeakReference](weakreference-class)\<T extends [Object](object-class)\>
:   A weak reference to a Dart object.

Extensions
----------

[EnumByName](enumbyname)
:   Access enum values by name.

[EnumName](enumname)
:   Access to the name of an enum value.

[FutureExtensions](../dart-async/futureextensions)
:   Convenience methods on futures.

Constants
---------

[deprecated](deprecated-constant) → const [Deprecated](deprecated-class)
:   Marks a feature as [Deprecated](deprecated-class) until the next
    release.
    <div>

    `Deprecated("next release")`

    </div>

[override](override-constant) → const [Object](object-class)
:   Annotation on an instance members which override an interface
    member.
    <div>

    `_Override()`

    </div>

[provisional](provisional-constant){.deprecated} → const [Null](null-class)
:   An annotation that was used during development of Dart 2.
    <div>

    `null`

    </div>

[proxy](proxy-constant){.deprecated} → const [Null](null-class)
:   This annotation was used in Dart prior to version 2.
    <div>

    `null`

    </div>

Functions
---------

[identical](identical)([Object](object-class)? a, [Object](object-class)? b) → [bool](bool-class)
:   Check whether two references are to the same object.

[identityHashCode](identityhashcode)([Object](object-class)? object) → [int](int-class)
:   The identity hash code of `object`.

[print](print)([Object](object-class)? object) → void
:   Prints a string representation of the object to the console.

Typedefs
--------

[Comparator](comparator)\<T\> = [int](int-class) Function(T a, T b)
:   The signature of a generic comparison function.

Exceptions / Errors {#exceptions}
-------------------

[AbstractClassInstantiationError](abstractclassinstantiationerror-class){.deprecated}
:   Error thrown when trying to instantiate an abstract class.

[ArgumentError](argumenterror-class)
:   Error thrown when a function is passed an unacceptable argument.

[AssertionError](assertionerror-class)
:   Error thrown by the runtime system when an assert statement fails.

[CastError](casterror-class){.deprecated}
:   Error thrown by the runtime system when a cast operation fails.

[ConcurrentModificationError](concurrentmodificationerror-class)
:   Error occurring when a collection is modified during iteration.

[CyclicInitializationError](cyclicinitializationerror-class)
:   Error thrown when a lazily initialized variable cannot be
    initialized.

[Error](error-class)
:   Error objects thrown in the case of a program failure.

[Exception](exception-class)
:   A marker interface implemented by all core library exceptions.

[FallThroughError](fallthrougherror-class)
:   Error thrown when control reaches the end of a switch case.

[FormatException](formatexception-class)
:   Exception thrown when a string or some other data does not have an
    expected format and cannot be parsed or processed.

[IndexError](indexerror-class)
:   A specialized [RangeError](rangeerror-class) used when an index is
    not in the range `0..indexable.length-1`.

[IntegerDivisionByZeroException](integerdivisionbyzeroexception-class){.deprecated}\
[NoSuchMethodError](nosuchmethoderror-class)
:   Error thrown by the default implementation of `noSuchMethod` on
    [Object](object-class).

[NullThrownError](nullthrownerror-class)
:   Error thrown when attempting to throw `null`.

[OutOfMemoryError](outofmemoryerror-class)
:   Error that the platform can use in case of memory shortage.

[RangeError](rangeerror-class)
:   Error thrown due to a value being outside a valid range.

[StackOverflowError](stackoverflowerror-class)
:   Error that the platform can use in case of stack overflow.

[StateError](stateerror-class)
:   The operation was not allowed by the current state of the object.

[TypeError](typeerror-class)
:   Error thrown by the runtime system when a dynamic type error
    happens.

[UnimplementedError](unimplementederror-class)
:   Thrown by operations that have not been implemented yet.

[UnsupportedError](unsupportederror-class)
:   The operation was not allowed by the object.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/dart-core-library.html>
:::
