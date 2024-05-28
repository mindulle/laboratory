[dart:html](../../dart-html/dart-html-library){._links-link}

supported property
==================

::: {#getter .section .multi-line-signature}
[bool](../../dart-core/bool-class) supported
:::

Checks if Real Time Communication (RTC) APIs are supported and enabled
on the current platform.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static bool get supported {
  // Currently in Firefox some of the RTC elements are defined but throw an
  // error unless the user has specifically enabled them in their
  // about:config. So we have to construct an element to actually test if RTC
  // is supported at the given time.
  try {
    new RtcPeerConnection({
      "iceServers": [
        {"url": "stun:localhost"}
      ]
    });
    return true;
  } catch (_) {
    return false;
  }
  return false;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/RtcPeerConnection/supported.html>
:::
