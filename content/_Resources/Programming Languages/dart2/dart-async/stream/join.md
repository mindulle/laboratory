[dart:async](../../dart-async/dart-async-library){._links-link}

join method
===========

::: {.section .multi-line-signature}
[Future](../future-class)\<[String](../../dart-core/string-class)\>
join(

1.  \[[String](../../dart-core/string-class) separator = \"\"\]

)
:::

Combines the string representation of elements into a single string.

Each element is converted to a string using its
[Object.toString](../../dart-core/object/tostring) method. If
`separator` is provided, it is inserted between element string
representations.

The returned future is completed with the combined string when this
stream is done.

If this stream emits an error, or the call to
[Object.toString](../../dart-core/object/tostring) throws, the returned
future is completed with that error, and processing stops.

Example:

``` {.language-dart data-language="dart"}
final result = await Stream.fromIterable(['Mars', 'Venus', 'Earth'])
    .join('--');
print(result); // 'Mars--Venus--Earth'
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
Future<String> join([String separator = ""]) {
  _Future<String> result = new _Future<String>();
  StringBuffer buffer = new StringBuffer();
  bool first = true;
  StreamSubscription<T> subscription =
      this.listen(null, onError: result._completeError, onDone: () {
    result._complete(buffer.toString());
  }, cancelOnError: true);
  subscription.onData(separator.isEmpty
      ? (T element) {
          try {
            buffer.write(element);
          } catch (e, s) {
            _cancelAndErrorWithReplacement(subscription, result, e, s);
          }
        }
      : (T element) {
          if (!first) {
            buffer.write(separator);
          }
          first = false;
          try {
            buffer.write(element);
          } catch (e, s) {
            _cancelAndErrorWithReplacement(subscription, result, e, s);
          }
        });
  return result;
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/join.html>
:::
