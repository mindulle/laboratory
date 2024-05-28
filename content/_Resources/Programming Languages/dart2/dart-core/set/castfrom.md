[dart:core](../../dart-core/dart-core-library){._links-link}

castFrom\<S, T\> method
=======================

::: {.section .multi-line-signature}
[Set](../set-class)\<T\> castFrom\<S, T\>(

1.  [Set](../set-class)\<S\> source,
2.  {[Set](../set-class)\<R\> newSet( )?}

)

::: {.features}
override
:::
:::

Adapts `source` to be a `Set<T>`.

If `newSet` is provided, it is used to create the new sets returned by
[toSet](toset), [union](union), and is also used for
[intersection](intersection) and [difference](difference). If `newSet`
is omitted, it defaults to creating a new set using the default
[Set](../set-class) constructor, and [intersection](intersection) and
[difference](difference) returns an adapted version of calling the same
method on the source.

Any time the set would produce an element that is not a `T`, the element
access will throw.

Any time a `T` value is attempted added into the adapted set, the store
will throw unless the value is also an instance of `S`.

If all accessed elements of `source` are actually instances of `T`, and
if all elements added to the returned set are actually instances of `S`,
then the returned set can be used as a `Set<T>`.

Methods which accept one or more `Object?` as argument, like
[contains](contains), [remove](remove) and [removeAll](removeall), will
pass the argument directly to the this set\'s method without any checks.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Set<T> castFrom<S, T>(Set<S> source, {Set<R> Function<R>()? newSet}) =>
    CastSet<S, T>(source, newSet);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Set/castFrom.html>
:::
