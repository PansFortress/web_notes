# Managing Application State
Often times, the state of an object might change but rather than having it consistently change the DOM. It's best practice to create an object to contain the state changes.

In this single state object example, we create a variable **state** and a functon **addItem** which takes in a state and an item. Everytime there is an event that will change the state, we append the change using the function:
```
var state = {
	items: []
};

var addItem = function(state, item){
	state.items.push(item);
};
```

Knowing that we intend to render the changes as a List item we create another function **renderList** which will create a new object containing the strings we want to render and then using jQuery's `element.html(x);` method to replace the entire contents of the element:

```
var renderList = function(state, element){
    var itemsHTML = state.items.map(function(item){
    	return '<li>' + item + '</li>';
    });
    element.html(itemsHTML);
};
```

Using the three functions above, we can use an event listener to trigger all three:

```
$('object').submit(function(event){
	event.preventDefault();
    addItem(state, $('inputFromObject').val());
    renderList(state, $('anotherObject'));
});
```