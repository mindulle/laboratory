[dart:html](../../dart-html/dart-html-library){._links-link}

isCharacterKey method
=====================

::: {.section .multi-line-signature}
[bool](../../dart-core/bool-class) isCharacterKey(

1.  [int](../../dart-core/int-class) keyCode

)
:::

Returns true if the keyCode produces a (US keyboard) character. Note:
This does not (yet) cover characters on non-US keyboards (Russian,
Hebrew, etc.).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
static bool isCharacterKey(int keyCode) {
  if ((keyCode >= ZERO && keyCode <= NINE) ||
      (keyCode >= NUM_ZERO && keyCode <= NUM_MULTIPLY) ||
      (keyCode >= A && keyCode <= Z)) {
    return true;
  }

  // Safari sends zero key code for non-latin characters.
  if (Device.isWebKit && keyCode == 0) {
    return true;
  }

  return (keyCode == SPACE ||
      keyCode == QUESTION_MARK ||
      keyCode == NUM_PLUS ||
      keyCode == NUM_MINUS ||
      keyCode == NUM_PERIOD ||
      keyCode == NUM_DIVISION ||
      keyCode == SEMICOLON ||
      keyCode == FF_SEMICOLON ||
      keyCode == DASH ||
      keyCode == EQUALS ||
      keyCode == FF_EQUALS ||
      keyCode == COMMA ||
      keyCode == PERIOD ||
      keyCode == SLASH ||
      keyCode == APOSTROPHE ||
      keyCode == SINGLE_QUOTE ||
      keyCode == OPEN_SQUARE_BRACKET ||
      keyCode == BACKSLASH ||
      keyCode == CLOSE_SQUARE_BRACKET);
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/KeyCode/isCharacterKey.html>
:::
