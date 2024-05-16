TypeError: cyclic object value
==============================


The JavaScript exception \"cyclic object value\" occurs when object
references were found in [JSON](https://www.json.org/).
[`JSON.stringify()`](../global_objects/json/stringify) doesn\'t try to
solve them and fails accordingly.



Message
-------


```text
TypeError: Converting circular structure to JSON (V8-based)
TypeError: cyclic object value (Firefox)
TypeError: JSON.stringify cannot serialize cyclic structures. (Safari)
```




Error type 
----------


[`TypeError`](../global_objects/typeerror)




What went wrong? 
----------------


The [JSON format](https://www.json.org/) per se doesn\'t support object
references (although an [IETF draft
exists](https://datatracker.ietf.org/doc/html/draft-pbryan-zyp-json-ref-03)),
hence [`JSON.stringify()`](../global_objects/json/stringify) doesn\'t
try to solve them and fails accordingly.




Examples
--------



### Circular references 


In a circular structure like the following



[js]


```js
const circularReference = { otherData: 123 };
circularReference.myself = circularReference;
```


[`JSON.stringify()`](../global_objects/json/stringify) will fail



[js]


```js
JSON.stringify(circularReference);
// TypeError: cyclic object value
```


To serialize circular references you can use a library that supports
them (e.g.
[cycle.js](https://github.com/douglascrockford/JSON-js/blob/master/cycle.js))
or implement a solution by yourself, which will require finding and
replacing (or removing) the cyclic references by serializable values.

The snippet below illustrates how to find and filter (thus causing data
loss) a cyclic reference by using the `replacer` parameter of
[`JSON.stringify()`](../global_objects/json/stringify):



[js]


```js
function getCircularReplacer() {
  const ancestors = [];
  return function (key, value) {
    if (typeof value !== "object" || value === null) {
      return value;
    }
    // `this` is the object that value is contained in,
    // i.e., its direct parent.
    while (ancestors.length > 0 && ancestors.at(-1) !== this) {
      ancestors.pop();
    }
    if (ancestors.includes(value)) {
      return "[Circular]";
    }
    ancestors.push(value);
    return value;
  };
}

JSON.stringify(circularReference, getCircularReplacer());
// {"otherData":123,"myself":"[Circular]"}

const o = {};
const notCircularReference = [o, o];
JSON.stringify(notCircularReference, getCircularReplacer());
// [{},{}]
```





See also 
--------


-   [`JSON.stringify()`](../global_objects/json/stringify)
-   [cycle.js](https://github.com/douglascrockford/JSON-js/blob/master/cycle.js)
    on GitHub




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Cyclic_object_value>

