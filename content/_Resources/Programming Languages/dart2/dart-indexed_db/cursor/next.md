[dart:indexed\_db](../../dart-indexed_db/dart-indexed_db-library){._links-link}

next method
===========

::: {.section .multi-line-signature}
<div>

1.  \@JSName(\'continue\')

</div>

void next(

1.  \[[Object](../../dart-core/object-class)? key\]

)

::: {.features}
\@JSName(\'continue\')
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@JSName('continue')
void next([Object? key]) {
  if (key == null) {
    JS('void', '#.continue()', this);
  } else {
    JS('void', '#.continue(#)', this, key);
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-indexed_db/Cursor/next.html>
:::
