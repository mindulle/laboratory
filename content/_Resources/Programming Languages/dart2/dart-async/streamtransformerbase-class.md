[dart:async](../dart-async/dart-async-library){._links-link}

StreamTransformerBase\<S, T\> class
===================================

Base class for implementing
[StreamTransformer](streamtransformer-class).

Contains default implementations of every method except
[bind](streamtransformer/bind).

Implemented types

:   -   [StreamTransformer](streamtransformer-class)\<S, T\>

Implementers

:   -   [Converter](../dart-convert/converter-class)
    -   [LineSplitter](../dart-convert/linesplitter-class)

Constructors
------------

[StreamTransformerBase](streamtransformerbase/streamtransformerbase)()

::: {.constructor-modifier .features}
const
:::

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[bind](streamtransformer/bind)([Stream](stream-class)\<S\> stream) →
[Stream](stream-class)\<T\>

::: {.features}
inherited
:::

Transforms the provided `stream`.

[cast](streamtransformerbase/cast)\<RS, RT\>() →
[StreamTransformer](streamtransformer-class)\<RS, RT\>

::: {.features}
override
:::

Provides a `StreamTransformer<RS, RT>` view of this stream transformer.

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

Operators
---------

[operator
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/StreamTransformerBase-class.html>
:::
