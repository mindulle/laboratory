[dart:async](../../dart-async/dart-async-library){._links-link}

Stream\<T\>.fromIterable constructor
====================================

::: {.section .multi-line-signature}
Stream\<T\>.fromIterable(

1.  [Iterable](../../dart-core/iterable-class)\<T\> elements

)
:::

Creates a stream that gets its data from `elements`.

The iterable is iterated when the stream receives a listener, and stops
iterating if the listener cancels the subscription, or if the
[Iterator.moveNext](../../dart-core/iterator/movenext) method returns
`false` or throws. Iteration is suspended while the stream subscription
is paused.

If calling [Iterator.moveNext](../../dart-core/iterator/movenext) on
`elements.iterator` throws, the stream emits that error and then it
closes. If reading [Iterator.current](../../dart-core/iterator/current)
on `elements.iterator` throws, the stream emits that error, but keeps
iterating.

Can be listened to more than once. Each listener iterates `elements`
independently.

Example:

``` {.language-dart data-language="dart"}
final numbers = [1, 2, 3, 5, 6, 7];
final stream = Stream.fromIterable(numbers);
```

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
factory Stream.fromIterable(Iterable<T> elements) =>
    Stream<T>.multi((controller) {
      Iterator<T> iterator;
      try {
        iterator = elements.iterator;
      } catch (e, s) {
        controller.addError(e, s);
        controller.close();
        return;
      }
      var zone = Zone.current;
      var isScheduled = true;

      void next() {
        if (!controller.hasListener || controller.isPaused) {
          // Cancelled or paused since scheduled.
          isScheduled = false;
          return;
        }
        bool hasNext;
        try {
          hasNext = iterator.moveNext();
        } catch (e, s) {
          controller.addErrorSync(e, s);
          controller.closeSync();
          return;
        }
        if (hasNext) {
          try {
            controller.addSync(iterator.current);
          } catch (e, s) {
            controller.addErrorSync(e, s);
          }
          if (controller.hasListener && !controller.isPaused) {
            zone.scheduleMicrotask(next);
          } else {
            isScheduled = false;
          }
        } else {
          controller.closeSync();
        }
      }

      controller.onResume = () {
        if (!isScheduled) {
          isScheduled = true;
          zone.scheduleMicrotask(next);
        }
      };

      zone.scheduleMicrotask(next);
    });
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-async/Stream/Stream.fromIterable.html>
:::
