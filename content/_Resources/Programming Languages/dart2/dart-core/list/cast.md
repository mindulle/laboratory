[dart:core](../../dart-core/dart-core-library){._links-link}

cast\<R\> method
================

::: {.section .multi-line-signature}
[List](../list-class)\<R\> cast\<R\>()

::: {.features}
override
:::
:::

Returns a view of this list as a list of `R` instances.

If this list contains only instances of `R`, all read operations will
work correctly. If any operation tries to read an element that is not an
instance of `R`, the access will throw instead.

Elements added to the list (e.g., by using [add](add) or
[addAll](addall)) must be instances of `R` to be valid arguments to the
adding function, and they must also be instances of `E` to be accepted
by this list as well.

Methods which accept `Object?` as argument, like
[contains](../iterable/contains) and [remove](remove), will pass the
argument directly to the this list\'s method without any checks. That
means that you can do `listOfStrings.cast<int>().remove("a")`
successfully, even if it looks like it shouldn\'t have any effect.

Typically implemented as `List.castFrom<E, R>(this)`.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
List<R> cast<R>();
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/List/cast.html>
:::
