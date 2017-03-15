
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
