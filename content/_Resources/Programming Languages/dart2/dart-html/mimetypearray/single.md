[dart:html](../../dart-html/dart-html-library){._links-link}

single property
===============

::: {#getter .section .multi-line-signature}
[MimeType](../mimetype-class) single

::: {.features}
override
:::
:::

Checks that this iterable has only one element, and returns that
element.

Throws a [StateError](../../dart-core/stateerror-class) if `this` is
empty or has more than one element.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
MimeType get single {
  int len = this.length;
  if (len == 1) {
    return JS('MimeType', '#[0]', this);
  }
  if (len == 0) throw new StateError("No elements");
  throw new StateError("More than one element");
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/MimeTypeArray/single.html>
:::
