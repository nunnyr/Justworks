Vue is reactive. It has a reactivity system that handles updates. When a data value changes, anywhere that relies on that data will automatically update. 

When we talk about data binding in Vue, we mean that the place where it is used or displayed in the template is directly linked, or bound to the source of the data, which is the data object inside the Vue instance. In other words, the host of the data is linked to the target of the data.

v-bind dynamically binds an attribute(like src) to an expression. In binding we are directly linking to the source of data. Usually this means the data object inside of the Vue instance.

Create chained conditional logic: 
 v-if 
 v-else-if 
 v-else 
 v-show (can change out visibility by adding display element of none.....toggles)

For list rendering you want to also provide each tag a key. It gives each DOM element a unique key. 


Instance is the object that a function returns. 


Key is just for vue engine (vdom) and it keeps track of how things are rerendered. Gives each DOM element a unique key. Vue can grasp on to the element and not lose it as it updates and changes in the app. Allows for performance. 

V-for works like a for loop. You write an alias and where you want to loop over. “detail in details” {{ detail }}.

V-on is a directive. So for example: v-on:click=”cart += 1”  is listening for a click event and it is triggering an expression. But what we to do here is have this v-on trigger a method. 
So it will be v-on:click=”addToCart”

You can add a style attribute and we bound the backgroundColor to it. And we gave it information (variant.color)

	:style=”{backgroundColor: variant.color}”
The inside of the expression is still javascript. Which is why we used camelCase for the backgroundColor property. Otherwise it would not have worked with background - color bc it would’ve thought we were doing math. 

You can also bind styles in data. 

Class binding: Multiple classes

<div class=”color-circle”
	:class=”{active: activeClass}”>
</div>

data(){
return {
activeClass: true

}
}

Here “active” is the class name and “activeClass” is the condition that we are evaluating for.
I could also use the ternary operators. 

:class=”[isActive ? activeClass : ‘’ ]”

:class=”{‘out-of-stock-img’: !inStock}”

            Here I am using quotes because this is a CSS property. If I used camelcase, it would be Js. And whenever it is not in stock, the opacity will be included. 

Computed properties: cache values and compute values for you. It will only update when it changes an update. In our socks store we are going to update the image, using an image path, and with each image we want to keep track of how many we have left.

Invalid template expression can occur when a for loop is not written properly.


A method is a function on a property of an object. A function is just a function. 



Const test = a



Computed properties will compute values based on their reactive dependency. Meaning computed properties will update, should a change occur. 

Dependencies are the data a function needs to run. 

Computed properties are storing functions and its values in memory. And will only update based on their reactive dependencies. Aka if the data that the function needs to run changes. A performance boost occurs because the computed property does not need to execute when it rerenders. 


A method property will run with every rerender. It rerenders in Vue when the state changes. 

=> a rerender is triggered by a change in state.



With event bubbling that is how a parent component 


Event bubbling means that the event moves from the child component to the parent component. Under the hood it is moving through the DOM and goes all the way up. 


//frontend