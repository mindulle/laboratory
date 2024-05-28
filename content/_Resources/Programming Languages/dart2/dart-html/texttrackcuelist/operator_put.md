[dart:html](../../dart-html/dart-html-library){._links-link}

operator \[\]= method
=====================

::: {.section .multi-line-signature}
void operator \[\]=(

1.  [int](../../dart-core/int-class) index,
2.  [TextTrackCue](../texttrackcue-class) value

)

::: {.features}
override
:::
:::

Sets the value at the given `index` in the list to `value`.

The `index` must be a valid index of this list, which means that `index`
must be non-negative and less than [length](length).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
void operator []=(int index, TextTrackCue value) {
  throw new UnsupportedError("Cannot assign element of immutable List.");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/TextTrackCueList/operator_put.html>
:::
