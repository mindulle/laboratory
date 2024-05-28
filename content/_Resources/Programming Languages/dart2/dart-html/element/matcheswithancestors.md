[dart:html](../../dart-html/dart-html-library){._links-link}

matchesWithAncestors method
===========================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) matchesWithAncestors(

1.  [String](../../dart-core/string-class) selectors

)
:::

Checks if this element or any of its parents match the CSS selectors.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool matchesWithAncestors(String selectors) {
  var elem = this as Element?;
  do {
    if (elem!.matches(selectors)) return true;
    elem = elem.parent;
  } while (elem != null);
  return false;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Element/matchesWithAncestors.html>
:::
