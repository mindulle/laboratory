TypeError: can\'t redefine non-configurable property \"x\"
==========================================================


The JavaScript exception \"can\'t redefine non-configurable property\"
occurs when it was attempted to redefine a property, but that property
is
[non-configurable](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#properties).



Message
-------


```text
TypeError: Cannot redefine property: "x" (V8-based)
TypeError: can't redefine non-configurable property "x" (Firefox)
TypeError: Attempting to change value of a readonly property. (Safari)
```




Error type 
----------


[`TypeError`](../global_objects/typeerror)




What went wrong? 
----------------


It was attempted to redefine a property, but that property is
[non-configurable](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#properties).
The `configurable` attribute controls whether the property can be
deleted from the object and whether its attributes (other than
`writable`) can be changed. Usually, properties in an object created by
an [object initializer](../operators/object_initializer) are
configurable. However, for example, when using
[`Object.defineProperty()`](../global_objects/object/defineproperty),
the property isn\'t configurable by default.




Examples
--------



### Non-configurable properties created by Object.defineProperty 


The [`Object.defineProperty()`](../global_objects/object/defineproperty)
creates non-configurable properties if you haven\'t specified them as
configurable.



[js]


```js
const obj = Object.create({});
Object.defineProperty(obj, "foo", { value: "bar" });

Object.defineProperty(obj, "foo", { value: "baz" });
// TypeError: can't redefine non-configurable property "foo"
```


You will need to set the \"foo\" property to configurable, if you intend
to redefine it later in the code.



[js]


```js
const obj = Object.create({});
Object.defineProperty(obj, "foo", { value: "bar", configurable: true });
Object.defineProperty(obj, "foo", { value: "baz", configurable: true });
```





See also 
--------


-   [\[\[Configurable\]\]](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures#properties)
-   [`Object.defineProperty()`](../global_objects/object/defineproperty)




© 2005--2023 MDN contributors.\
Licensed under the Creative Commons Attribution-ShareAlike License v2.5
or later.\
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Cant_redefine_property>

