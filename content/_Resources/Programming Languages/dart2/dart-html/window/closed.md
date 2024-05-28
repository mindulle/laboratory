[dart:html](../../dart-html/dart-html-library){._links-link}

closed property
===============

::: {#getter .section .multi-line-signature}
[bool](../../dart-core/bool-class)? closed

::: {.features}
override
:::
:::

Indicates whether this window has been closed.

``` {.language-dart data-language="dart"}
print(window.closed); // 'false'
window.close();
print(window.closed); // 'true'
```

MDN does not have compatibility info on this attribute, and therefore is
marked nullable.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool? get closed native;
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Window/closed.html>
:::
