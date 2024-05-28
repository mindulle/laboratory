[dart:html](../../dart-html/dart-html-library){._links-link}

getGamepads method
==================

::: {.section .multi-line-signature}
[List](../../dart-core/list-class)\<[Gamepad](../gamepad-class)?\>
getGamepads()
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
List<Gamepad?> getGamepads() {
  var gamepadList = _getGamepads();

  // If no prototype we need one for the world to hookup to the proper Dart class.
  var jsProto = JS('', '#.prototype', gamepadList);
  if (jsProto == null) {
    JS('', '#.prototype = Object.create(null)', gamepadList);
  }

  applyExtension('GamepadList', gamepadList);
  return gamepadList;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/Navigator/getGamepads.html>
:::
