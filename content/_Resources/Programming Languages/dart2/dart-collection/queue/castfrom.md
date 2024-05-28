[dart:collection](../../dart-collection/dart-collection-library){._links-link}

castFrom\<S, T\> method
=======================

::: {.section .multi-line-signature}
[Queue](../queue-class)\<T\> castFrom\<S, T\>(

1.  [Queue](../queue-class)\<S\> source

)

::: {.features}
override
:::
:::

Adapts `source` to be a `Queue<T>`.

Any time the queue would produce an element that is not a `T`, the
element access will throw.

When a `T` value is stored into the adapted queue, the operation will
throw unless the value is also an instance of `S`.

If all accessed elements of `source` are actually instances of `T`, and
if all elements stored into the returned queue are actually instances of
`S`, then the returned queue can be used as a `Queue<T>`.

Methods which accept `Object?` as argument, like
[contains](../../dart-core/iterable/contains) and [remove](remove), will
pass the argument directly to this queue\'s method without any checks.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Queue<T> castFrom<S, T>(Queue<S> source) => CastQueue<S, T>(source);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-collection/Queue/castFrom.html>
:::
