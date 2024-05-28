[dart:core](../../dart-core/dart-core-library){._links-link}

apply method
============

::: {.section .multi-line-signature}
dynamic apply(

1.  [Function](../function-class) function,
2.  [List](../list-class)? positionalArguments,
3.  \[[Map](../map-class)\<[Symbol](../symbol-class), dynamic\>?
    namedArguments\]

)
:::

Dynamically call `function` with the specified arguments.

Acts the same as calling function with positional arguments
corresponding to the elements of `positionalArguments` and named
arguments corresponding to the elements of `namedArguments`.

This includes giving the same errors if `function` isn\'t callable or if
it expects different parameters.

Example:

``` {.language-dart data-language="dart"}
void printWineDetails(int vintage, {String? country, String? name}) {
  print('Name: $name, Country: $country, Vintage: $vintage');
}

void main() {
  Function.apply(
      printWineDetails, [2018], {#country: 'USA', #name: 'Dominus Estate'});
}

// Output of the example is:
// Name: Dominus Estate, Country: USA, Vintage: 2018
```

If `positionalArguments` is null, it\'s considered an empty list. If
`namedArguments` is omitted or null, it is considered an empty map.

``` {.language-dart data-language="dart"}
void helloWorld() {
  print('Hello world!');
}

void main() {
  Function.apply(helloWorld, null);
}
// Output of the example is:
// Hello world!
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
external static apply(Function function, List<dynamic>? positionalArguments,
    [Map<Symbol, dynamic>? namedArguments]);
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-core/Function/apply.html>
:::
