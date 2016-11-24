# TODOs for Learning and Improving
1. Review jQuery selectors
```
$('.shopping-list').on('click','.shopping-item-toggle',(function(event){
	var itemToToggle = $(this).closest("li").find(".shopping-item").text();
    //do more stuff
```

Above example is listening for a click event within `.shopping-list` class on any item labeled `.shopping-item-toggle`.

```
<li>
	<div class = 'shopping-item'></div>
    <div class = 'shopping-item-toggle'></div>
    <div class = 'shopping-item-cancel'></div>
</li>
```
Using the above HTML structure, `var itemToToggle` is searching on itself for the nearest `li` element up the chain and ignore `.shopping-item`. We need to utilize `find` to grab the nearest `.shopping-item` down the chain.