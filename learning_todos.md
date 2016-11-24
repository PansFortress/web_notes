# TODOs for Learning and Improving
1. Review jQuery selectors
```
$('.shopping-list').on('click','.shopping-item-toggle',(function(event){
	var itemToToggle = $(this).closest("li").find(".shopping-item").text();
    //do more stuff
```
Above example is listening for a click event within `.shopping-list` class on any item labeled `.shopping-item-toggle`.