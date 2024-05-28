[dart:html](../../dart-html/dart-html-library){._links-link}

matchingTarget property
=======================

::: {#getter .section .multi-line-signature}
[Element](../element-class) matchingTarget

::: {.features}
inherited
:::
:::

A pointer to the element whose CSS selector matched within which an
event was fired. If this Event was not associated with any Event
delegation, accessing this value will throw an
[UnsupportedError](../../dart-core/unsupportederror-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Element get matchingTarget {
  if (_selector == null) {
    throw new UnsupportedError('Cannot call matchingTarget if this Event did'
        ' not arise as a result of event delegation.');
  }
  Element? currentTarget = this.currentTarget as Element?;
  Element? target = this.target as Element?;
  do {
    if (target!.matches(_selector!)) return target;
    target = target.parent;
  } while (target != null && target != currentTarget!.parent);
  throw new StateError('No selector matched for populating matchedTarget.');
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/KeyEvent/matchingTarget.html>
:::
