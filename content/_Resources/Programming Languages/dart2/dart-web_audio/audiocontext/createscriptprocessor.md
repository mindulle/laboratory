[dart:web\_audio](../../dart-web_audio/dart-web_audio-library){._links-link}

createScriptProcessor method
============================

::: {.section .multi-line-signature}
[ScriptProcessorNode](../scriptprocessornode-class)
createScriptProcessor(

1.  \[[int](../../dart-core/int-class)? bufferSize,
2.  [int](../../dart-core/int-class)? numberOfInputChannels,
3.  [int](../../dart-core/int-class)? numberOfOutputChannels\]

)

::: {.features}
override
:::
:::

Implementation {#source}
--------------

``` {.language-dart data-language="dart"}
ScriptProcessorNode createScriptProcessor(
    [int? bufferSize,
    int? numberOfInputChannels,
    int? numberOfOutputChannels]) {
  var function = JS(
      '=Object',
      '#.createScriptProcessor || '
          '#.createJavaScriptNode',
      this,
      this);
  if (numberOfOutputChannels != null) {
    return JS('ScriptProcessorNode', '#.call(#, #, #, #)', function, this,
        bufferSize, numberOfInputChannels, numberOfOutputChannels);
  } else if (numberOfInputChannels != null) {
    return JS('ScriptProcessorNode', '#.call(#, #, #)', function, this,
        bufferSize, numberOfInputChannels);
  } else if (bufferSize != null) {
    return JS(
        'ScriptProcessorNode', '#.call(#, #)', function, this, bufferSize);
  } else {
    return JS('ScriptProcessorNode', '#.call(#)', function, this);
  }
}
```

::: {._attribution}
© 2012 the Dart project authors\
Licensed under the BSD 3-Clause \"New\" or \"Revised\" License.\
<https://api.dart.dev/stable/2.18.5/dart-web_audio/AudioContext/createScriptProcessor.html>
:::
