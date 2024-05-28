[dart:html](../../dart-html/dart-html-library){._links-link}

operator \[\] method
====================

::: {.section .multi-line-signature}
[File](../file-class) operator \[\](

1.  [int](../../dart-core/int-class) index

)

::: {.features}
override
:::
:::

The object at the given `index` in the list.

The `index` must be a valid index of this list, which means that `index`
must be non-negative and less than [length](length).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
File operator [](int index) {
  if (JS("bool", "# >>> 0 !== # || # >= #", index, index, index, length))
    throw new RangeError.index(index, this);
  return JS("File", "#[#]", this, index);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/FileList/operator_get.html>
:::
