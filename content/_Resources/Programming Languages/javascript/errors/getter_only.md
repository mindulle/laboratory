TypeError: setting getter-only property \"x\"
=============================================


The JavaScript [strict mode](../strict_mode)-only exception \"setting
getter-only property\" occurs when there is an attempt to set a new
value to a property for which only a [getter](../functions/get) is
specified.



Message
-------


```text
TypeError: Cannot set property x of #<Object> which has only a getter (V8-based)
TypeError: setting getter-only property "x" (Firefox)
TypeError: Attempted to assign to readonly property. (Safari)
```




Error type 
----------


[`TypeError`](../global_objects/typeerror) in [strict
mode](../strict_mode) only.




What went wrong? 
----------------


There is an attempt to set a new value to a property for which only a
[getter](../functions/get) is specified. While this will be silently
ignored in non-strict mode, it will throw a
[`TypeError`](../global_objects/typeerror) in [strict
mode](../strict_mode).




Examples
--------



### Property with no setter 


The example below shows how to set a getter for a property. It doesn\'t
specify a [setter](../functions/set), so a `TypeError` will be thrown
upon trying to set the `temperature` property to `30`. For more details
see also the
[`Object.defineProperty()`](../global_objects/object/defineproperty)
page.



[js]


```js
"use strict";

function Archiver() {
  const temperature = null;
  Object.defineProperty(this, "temperature", {
    get() {
      console.log("get!");
      return temperature;
    },
  });
}

const arc = new Archiver();
arc.temperature; // 'get!'

arc.temperature = 30;
// TypeError: setting getter-only property "temperature"
```


To fix this error, you will either need to remove line 16, where there
is an attempt to set the temperature property, or you will need to
implement a [setter](../functions/set) for it, for example like this:



[js]


```js
"use strict";

function Archiver() {
  let temperature = null;
  const archive = [];

  Object.defineProperty(this, "temperature", {
    get() {
      console.log("get!");
      return temperature;
    },
    set(value) {
      temperature = value;
      archive.push({ val: temperature });
    },
  });

  this.getArchive = function () {
    return archive;
  };
}

const arc = new Archiver();
arc.temperature; // 'get!'
arc.temperature = 11;
arc.temperature = 13;
arc.getArchive(); // [{ val: 11 }, { val: 13 }]
```





See also 
--------


-   [`Object.defineProperty()`](../global_objects/object/defineproperty)
-   [`Object.defineProperties()`](../global_objects/object/defineproperties)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Getter_only>

