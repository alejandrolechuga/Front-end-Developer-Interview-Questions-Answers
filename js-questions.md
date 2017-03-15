
1. ### Explain event delegation  
Event delegation is basically taking advantange of the event bubbling. So if we have an element containing child nodes and we want to listen the event of the child nodes , then we can set the event listener on parent node and then handle the events originated by the child nodes. 

```javascript 
var parent = document.getElementById('parent');
parent.addEventListener('click', clickHandler);

function clickHandler (event) {
  var target = event.target;
  if (target.matches('li.odd'))  {
    console.log('li ! odd');
  }
}
```

2. ### Explain how `this` works in JavaScript
The this reference evaluates the current execution context, for example if you run it in the global scope it will point to the global object (window in browsers) , if you excute it withing an object method it will refer to that object. You can also use the function method bind which you can specify the context. As well with methods like call and apply. 

3. ### Explain how prototypal inheritance works
- TODO - Object.create, function.bind

4. ### What do you think of AMD vs CommonJS? 
- TODO 

5. ### Explain why the following doesn't work as an IIFE: function foo(){ }();.
   ### What needs to be changed to properly make it an IIFE?
   
   
6. ### What's the difference between a variable that is: null, undefined or undeclared?
   *undeclared* is when you try to point to a variable that doens't exist or never was created and produces a fatal error.
   *undefined* is when you declare a variable but never assgined a value.  
   *null* is a value that expresses the lack of value, you can use it as placeholder.
   ### How would you go about checking for any of these states? 
   ```javascript
     // undeclared  and undefined 
    if ( typeof variable === 'undefined' ) {} 
    // check if is null
    if ( variable === nulll ) {}
   ```
 7. ##3 What is a closure, and how/why would you use one? 
   A clousure is when a function scope can be acccessed by another function , keeping variables in memory as long this function is referenceable. 
   How ? 
  ```javascript 
      function increase(number) {
         return function () {
           return ++number;
         }
      }
      var increaseFive = increase(5); 
      increaseFive() // => 6
      increaseFive() // => 7 
      increaseFive() // => 8
    ```
    Why? It can be useful to cache values, to make private variables , and you can use the module pattern for exposing just certain properties of your modules. 
