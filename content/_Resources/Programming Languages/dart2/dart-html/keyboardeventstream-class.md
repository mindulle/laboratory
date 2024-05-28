[dart:html](../dart-html/dart-html-library){._links-link}

KeyboardEventStream class
=========================

Records KeyboardEvents that occur on a particular element, and provides
a stream of outgoing KeyEvents with cross-browser consistent keyCode and
charCode values despite the fact that a multitude of browsers that have
varying keyboard default behavior.

Example usage:

``` {.language-dart data-language="dart"}
KeyboardEventStream.onKeyDown(document.body).listen(
    keydownHandlerTest);
```

This class is very much a work in progress, and we\'d love to get
information on how we can make this class work with as many
international keyboards as possible. Bugs welcome!

Constructors
------------

[KeyboardEventStream](keyboardeventstream/keyboardeventstream)()

Properties {#instance-properties}
----------

[hashCode](../dart-core/object/hashcode) → [int](../dart-core/int-class)

::: {.features}
read-only, inherited
:::

The hash code for this object.

[runtimeType](../dart-core/object/runtimetype) →
[Type](../dart-core/type-class)

::: {.features}
read-only, inherited
:::

A representation of the runtime type of the object.

Methods {#instance-methods}
-------

[noSuchMethod](../dart-core/object/nosuchmethod)([Invocation](../dart-core/invocation-class)
invocation) → dynamic

::: {.features}
inherited
:::

Invoked when a non-existent method or property is accessed.

[toString](../dart-core/object/tostring)() →
[String](../dart-core/string-class)

::: {.features}
inherited
:::

A string representation of this object.

Operators
---------

[operator
==](../dart-core/object/operator_equals)([Object](../dart-core/object-class)
other) → [bool](../dart-core/bool-class)

::: {.features}
inherited
:::

The equality operator.

Static Methods
--------------

[onKeyDown](keyboardeventstream/onkeydown)([EventTarget](eventtarget-class) target) → [CustomStream](customstream-class)\<[KeyEvent](keyevent-class)\>
:   Named constructor to produce a stream for onKeyDown events.

[onKeyPress](keyboardeventstream/onkeypress)([EventTarget](eventtarget-class) target) → [CustomStream](customstream-class)\<[KeyEvent](keyevent-class)\>
:   Named constructor to produce a stream for onKeyPress events.

[onKeyUp](keyboardeventstream/onkeyup)([EventTarget](eventtarget-class) target) → [CustomStream](customstream-class)\<[KeyEvent](keyevent-class)\>
:   Named constructor to produce a stream for onKeyUp events.

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-html/KeyboardEventStream-class.html>
:::
