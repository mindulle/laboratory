[dart:core](../../dart-core/dart-core-library){._links-link}

operator == method
==================

::: {.section .multi-line-signature}
[bool](../bool-class) operator ==(

1.  [Object](../object-class) other

)

::: {.features}
override
:::
:::

Test whether another object is equal to this function.

Function objects are only equal to other function objects (an object
satisfying `object is Function`), and never to non-function objects.

Some function objects are considered equal by `==` because they are
recognized as representing the \"same function\":

-   It is the same object. Static and top-level functions are compile
    time constants when used as values, so referring to the same
    function twice always give the same object, as does referring to a
    local function declaration twice in the same scope where it was
    declared.
-   if they refer to the same member method extracted from the same
    object. Repeatedly extracting an instance method of an object as a
    function value gives equal, but not necessarily identical, function
    values.

Different evaluations of function literals never give rise to equal
function objects. Each time a function literal is evaluated, it creates
a new function value that is not equal to any other function value, not
even ones created by the same expression.

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
bool operator ==(Object other);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Function/operator_equals.html>
:::
