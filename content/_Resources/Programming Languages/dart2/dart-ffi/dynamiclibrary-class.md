[dart:ffi](../dart-ffi/dart-ffi-library){._links-link}

DynamicLibrary class
====================

A dynamically loaded native library.

A dynamically loaded library is a mapping from symbols to memory
addresses. These memory addresses can be accessed through
[lookup](dynamiclibrary/lookup).

Available Extensions

:   -   [DynamicLibraryExtension](dynamiclibraryextension)

Constructors
------------

[DynamicLibrary.executable](dynamiclibrary/dynamiclibrary.executable)()

::: {.constructor-modifier .features}
factory
:::

Creates a [DynamicLibrary](dynamiclibrary-class) containing all the
symbols of the running executable.

[DynamicLibrary.open](dynamiclibrary/dynamiclibrary.open)([String](../dart-core/string-class)
path)

::: {.constructor-modifier .features}
factory
:::

Loads a library file and provides access to its symbols.

[DynamicLibrary.process](dynamiclibrary/dynamiclibrary.process)()

::: {.constructor-modifier .features}
factory
:::

Creates a [DynamicLibrary](dynamiclibrary-class) holding all global
symbols.

Properties {#instance-properties}
----------

[handle](dynamiclibrary/handle) →
[Pointer](pointer-class)\<[Void](void-class)\>

::: {.features}
read-only
:::

The opaque handle to the dynamic library.

[hashCode](dynamiclibrary/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, override
:::

The hash code for a [DynamicLibrary](dynamiclibrary-class) only depends
on the loaded library.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[lookup](dynamiclibrary/lookup)\<T extends
[NativeType](nativetype-class)\>([String](../dart-core/string-class)
symbolName) → [Pointer](pointer-class)\<T\>

Looks up a symbol in the [DynamicLibrary](dynamiclibrary-class) and
returns its address in memory.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[providesSymbol](dynamiclibrary/providessymbol)([String](../dart-core/string-class)
symbolName) → [bool](../dart-core/bool-class)

::: {.features}
\@Since(\'2.14\')
:::

Checks whether this dynamic library provides a symbol with the given
name.

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

Operators
---------

[operator
==](dynamiclibrary/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
override
:::

Dynamic libraries are equal if they load the same library.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-ffi/DynamicLibrary-class.html>
:::
