[dart:html](../../dart-html/dart-html-library){._links-link}

KeyEvent.wrap constructor
=========================

::: {.section .multi-line-signature}
KeyEvent.wrap(

1.  [KeyboardEvent](../keyboardevent-class) parent

)
:::

Construct a KeyEvent with `parent` as the event we\'re emulating.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
KeyEvent.wrap(KeyboardEvent parent)
    : _parent = parent,
      _shadowAltKey = false,
      _shadowCharCode = 0,
      _shadowKeyCode = 0,
      super(parent) {
  _parent = parent;
  _shadowAltKey = _realAltKey;
  _shadowCharCode = _realCharCode;
  _shadowKeyCode = _realKeyCode;
  _currentTarget = _parent.currentTarget;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/KeyEvent/KeyEvent.wrap.html>
:::
