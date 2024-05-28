[dart:developer](../../dart-developer/dart-developer-library){._links-link}

begin method
============

::: {.section .multi-line-signature}
[Flow](../flow-class) begin(

1.  {[int](../../dart-core/int-class)? id}

)
:::

A \"begin\" Flow event.

When passed to a [Timeline](../timeline-class) method, generates a
\"begin\" Flow event. If `id` is not provided, an id that conflicts with
no other Dart-generated flow id\'s will be generated.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static Flow begin({int? id}) {
  return new Flow._(_begin, id ?? _getNextAsyncId());
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-developer/Flow/begin.html>
:::
