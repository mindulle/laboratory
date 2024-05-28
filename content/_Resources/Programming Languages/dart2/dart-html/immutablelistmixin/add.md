[dart:html](../../dart-html/dart-html-library){._links-link}

add method
==========

::: {.section .multi-line-signature}
void add(

1.  E value

)

::: {.features}
override
:::
:::

Adds `value` to the end of this list, extending the length by one.

The list must be growable.

``` {.language-dart data-language="dart"}
final numbers = <int>[1, 2, 3];
numbers.add(4);
print(numbers); // [1, 2, 3, 4]
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void add(E value) {
  throw new UnsupportedError("Cannot add to immutable List.");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/ImmutableListMixin/add.html>
:::
