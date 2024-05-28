[dart:core](../../dart-core/dart-core-library){._links-link}

List\<E\>.empty constructor
===========================

::: {.section .multi-line-signature}
<div>

1.  \@Since(\"2.9\")

</div>

List\<E\>.empty(

1.  {[bool](../bool-class) growable = false}

)
:::

Creates a new empty list.

If `growable` is `false`, which is the default, the list is a
fixed-length list of length zero. If `growable` is `true`, the list is
growable and equivalent to `<E>[]`.

``` {.language-dart data-language="dart"}
final growableList = List.empty(growable: true); // []
growableList.add(1); // [1]

final fixedLengthList = List.empty(growable: false);
fixedLengthList.add(1); // error
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@Since("2.9")
external factory List.empty({bool growable = false});
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/List/List.empty.html>
:::
