[dart:core](../../dart-core/dart-core-library){._links-link}

noSuchMethod method
===================

::: {.section .multi-line-signature}
dynamic noSuchMethod(

1.  [Invocation](../invocation-class) invocation

)
:::

Invoked when a non-existent method or property is accessed.

A dynamic member invocation can attempt to call a member which doesn\'t
exist on the receiving object. Example:

``` {.language-dart data-language="dart"}
dynamic object = 1;
object.add(42); // Statically allowed, run-time error
```

This invalid code will invoke the `noSuchMethod` method of the integer
`1` with an [Invocation](../invocation-class) representing the
`.add(42)` call and arguments (which then throws).

Classes can override [noSuchMethod](nosuchmethod) to provide custom
behavior for such invalid dynamic invocations.

A class with a non-default [noSuchMethod](nosuchmethod) invocation can
also omit implementations for members of its interface. Example:

``` {.language-dart data-language="dart"}
class MockList<T> implements List<T> {
  noSuchMethod(Invocation invocation) {
    log(invocation);
    super.noSuchMethod(invocation); // Will throw.
  }
}
void main() {
  MockList().add(42);
}
```

This code has no compile-time warnings or errors even though the
`MockList` class has no concrete implementation of any of the `List`
interface methods. Calls to `List` methods are forwarded to
`noSuchMethod`, so this code will `log` an invocation similar to
`Invocation.method(#add, [42])` and then throw.

If a value is returned from `noSuchMethod`, it becomes the result of the
original invocation. If the value is not of a type that can be returned
by the original invocation, a type error occurs at the invocation.

The default behavior is to throw a
[NoSuchMethodError](../nosuchmethoderror-class).

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
@pragma("vm:entry-point")
external dynamic noSuchMethod(Invocation invocation);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Object/noSuchMethod.html>
:::
