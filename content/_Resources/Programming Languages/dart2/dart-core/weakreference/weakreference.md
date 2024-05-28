[dart:core](../../dart-core/dart-core-library){._links-link}

WeakReference\<T extends Object\> constructor
=============================================

::: {.section .multi-line-signature}
WeakReference\<T extends Object\>(

1.  T target

)
:::

Creates a [WeakReference](../weakreference-class) pointing to the given
`target`.

The `target` must be an object supported as an
[Expando](../expando-class) key, which means `target` cannot be a
number, a string, a boolean, the `null` value, or certain other types of
special objects.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external factory WeakReference(T target);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/WeakReference/WeakReference.html>
:::
