<!--
Creator: Ilias Tsangaris
Market: SF
Adapted By: Zeb Girouard
Market: DEN
-->

![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png)

<!--WDI5 9:32 -->
<!--Actually 10:40  -->
<!--WDI4 9:40 -->
<!-- 9:30 15 minutes -->

<!-- Hook - Think about a game of soccer.  Let's think about all the pieces that make up that game, what are they?  What are some of their properties, things that describe them?  How about their methods, what do they do?  Pause for 1 minute, then cold-call and write this in JSON on white board as students fill in details.  
-->

<!--This whole class, you basically don't need to show this README, just type live into the Dev Tools Console -->

# Flower Power: Object Oriented Programming in JavaScript

## Why is this important?
<!-- framing the "why" in big-picture/real world examples -->
*This workshop is important because:*

Object oriented programming is a common pattern throughout many languages. Its patterns will enable you to write more readable, organized, and declarative programs.

## What are the objectives?
<!-- specific/measurable goal for students to achieve -->
*After this workshop, developers will be able to:*

- **Build** practical and useful objects using Javascript constructors
- **Demonstrate** a working knowledge of  object properties and methods

## Where should we be now?
<!-- call out the skills that are prerequisites -->
*Before this workshop, developers should already be able to:*

- Comfortably **implement** JavaScript objects & functions

## Review: What is an Object?

As of today, we have been writing our Javascript code using mainly functions, Strings, numbers, and Arrays.   This has allowed us to parse through data objects given to us, reach out and pull data from the internet, and display it all on a web page!  These are all great accomplishments, but like everything else in the world of programming, there is always a more efficient way of implementing what we have done.

Here's a truncated version of some cohort data.  Take some time to study the structure and the data types within the data object.

```javascript
var cohort = {
	school: "General Assembly",
	city: "Denver",
	course: "Web Development Immersive",
	courseId: "WDI5",
	classroom: "Grays",
	students: [{
		id: 0,
		lastName: "Girouard",
		firstName: "Zeb",
		githubUsername: "zebgirouard"
	}, {
		id: 1,
		lastName: "Anderson",
		firstName: "Nick",
		githubUsername: "nickandersonr"
	}]
}


```

-  Based on our experience in class so far and your familiarity with the above object, consider the following as you read further:
	- How many of the properties in `cohort` are Strings? 
 	- How many of the properties are Arrays?
 	- If there is an array, what data type(s) are the elements inside?

<!-- CFU: Think-Pair-Share -->

<!--WDI5 9:44 -->

The `cohort` object is a grouping of key & value pairs (known as properties) that describe our class.  
  
```javascript 
school: "General Assembly"
```
In the line above, `school` is the **key** and `"General Assembly"` is the **value**.
 
To access a property, we can use dot-notation or bracket-notation on the key to have the corresponding value returned.
 
 ```javascript
 var GA = cohort.school; //General Assembly
 ```

 ```javascript
 var GA = cohort["school"]; //General Assembly
 ```
 
Now the variable `GA` is assigned to the string `General Assembly`.  

How about if we want to access all the cohort's students?

 ```javascript
 var students = cohort.students; //students
 ```
The `cohort.students` array is now accessible by using `students` instead.
Declaring variables and defining them as portions of a larger object helps us create readable and maintainable code.  

*We can assume that an Object is a collection of properties (key & value pairs) that all have some sort of relationship, connected logically to one another.*  

<!--CFU: Fist-to-five on Object properties, methods -->

<!--WDI5 9:48 -->
<!--WDI4 9:56 -->
<!--Actually 10:54 -->
# Quick Challenge
<!-- 9:45 5 minutes -->
- Add some more properties that would fit into an object describing our cohort (address, floor number, instructors, etc).
- Try to access your new properties from the console to make sure they work.

If everything worked out, you should have a fully functioning `cohort` object, only now with even MORE properties for us to play with!  

<!-- Actually 11:00 -->
<!--WDI5 9:53 -->
<!--10:05 WDI4 -->
## Creating Objects
<!-- 9:50 10 minutes-->
For relatively straightforward and small objects, it is perfectly fine to declare them as a variable and define them, as we did with `cohort`.  This is known as a *Literal* object definition.  

### Literal Method

Here's a flower using the *Literal* method:

```javascript
// Literal Object Definition
let flower = {
	color : "red",
	petals : 32,
	smells : true
};
```

### Constructor Syntax

Now let's explore a flower using the preferred *constructor* syntax:
 
 ```javascript
 // constructor object definition
 // note: constructors are always capitalized by convention
 function Flower() {
 	this.color = "red";
 	this.petals = 32;
 	this.smells= true;
 }
 ```

The constructor method is actually a function that can create unique instances of flower objects every time it is called.  Below, we will create a variable `tulip` that will use the constructor method to create a new object.

```javascript
// the keyword `new` is necessary
let tulip = new Flower();
```

Let us break down a couple concepts introduced with this new line of code:
- The capitalization of `Flower` lets everyone know that `Flower` is an object constructor.  Calling `Flower()` will return a `Flower` object.
- The `new` keyword before our function tells javascript that we are creating a new object that will be independent of any other object.
- We call the flower function, which creates an object with the properties made.  Our object is ready to go!

<img src = http://www.mzephotos.com/wallpapers/roses/red-rose-1024x768.jpg width = 75%>

### Independent Practice

Now imagine a specific flower.  Take a few minutes to think of three properties.  Try to use multiple senses to describe it.  Then, use a *constructor* called `Flower` to make a new type of flower with a couple different properties.  Print your new flower to the console to see what it looks like.

<!--CFU Fist-to-five on the two main ways to create an object -->

<!--Actually 11:11 -->
<!--WDI4 10:16 but basically did next section already -->
<!--WDI5 10:03 -->
<!-- 10:00 5 minutes-->

### Taking It Further

Accessing the properties of our new `tulip` object is the same as accessing our properties from any other object: we can use either dot or bracket notation.

```javascript
let color = tulip.color; // red
let petalCount = tulip.petals; // 32
let smellsNice = tulip.smells; //true
```

If we wanted to create yet ANOTHER flower, all we have to do is call our function just like we did above.  This time, let's make an object called `lily`.

```javascript
let lily = new Flower();
```

We can access the properties of `lily` in the same manner as we did with `tulip`.

```javascript
let color = lily.color; // red
let petalCount = lily.petals; // 32
let smellsNice = lily.smells; //true
```

I don't know about you, but I generally like my lilies yellow. I have also never heard of a lily with 32 petals, holy smokes!  Can we change our `lily` object to better reflect my perfect lily? You bet!

```javascript
// Changing object property values
lily.color = 'yellow';
lily.petals = 6;
```

That's more like it!  To change the value of the lily object properties, we simply access them with dot or bracket notation.  We then follow with an equals and a new appropriate value.  Couldn't be easier!

<img src = https://seniorhikerphotos.files.wordpress.com/2012/06/lilysarina12052301.jpg width = 75%>

<!--11:12 -->
## Object Methods
<!-- 10:05 10 minutes -->
One of the most powerful features of Javascript Objects are Methods.  Methods are *"functions"* that are predefined and built into an object.  We all know and love `Array` methods like `forEach()`, `map()`, `filter()`, and `reduce()`; these are all Methods of the Array object.  We use arrays so much that Javascript automagically creates them from an Array constructor without us having to instantiate them with `new` like we did above with the flowers.  Thanks, Javascript!

Let's make a simple method in the flower object that outputs to the console whenever we call it.

```javascript
function Flower() {
    this.color = "red";
    this.petals = 32;
    this.smells= true;
    // Demonstrates a simple method in an object
    this.bloom = function() {
        console.log("Look at me!");
    };
}
```

We now have a method inside our flower object called `bloom`.

There's an issue with the above code. If we create multiple flowers we don't care if the properties `color`, `petal`, and `smells` all have different values. It makes sense for these properties to be different and customizable for each flower. However, all flowers could share the `bloom` method. What we want to avoid is creating an entirely new `bloom` method every time we make a new flower.

```javascript
let lily = new Flower();
let rose = new Flower();

lily.bloom === rose.bloom // false
```

But we want their bloom methods to be the same!

<!-- CFU: Why is this?  (Similar to objectA and objectB not being equal even though they have same properties) -->

## Prototypes

<!--10:09 WDI5 -->
<!-- 10:15 10 minutes -->

By adding the method `bloom` to the constructor's **prototype** we can enable all flowers to share a `bloom` method, or any other method for that matter! The prototype is simply the object that can be referenced by all the flower instances.

```javascript
function Flower() {
    this.color = "red";
    this.petals = 32;
    this.smells= true;
}

Flower.prototype = {
  bloom: function() {
    console.log("Look at me!");
  }
}
```

Now try running the same test to see if both flowers share the same `bloom` method.

```javascript
let lily = new Flower();
let rose = new Flower();

lily.bloom === rose.bloom // true
```

### Benefits of Putting Methods in Prototypes
- Less wasted memory
- Single source of truth

### Check for Yourself

What if we edit the prototype *after* the flower instances have been created? Will they update their behavior accordingly?

<!--WDI5 10:20 -->
<!--11:27 -->
<!--10:26 WDI4-->
### More methods
<!-- 10:25 5 minutes-->
Let's add some more methods to the flower prototype.

```javascript
function Flower() {
    this.color = "red";
    this.petals = 32;
    this.smells= true;
}

Flower.prototype = {
  bloom: function() {
    console.log("Look at me!");
  },
  smellsGood: function() {
  // use `this` to access the instance's attributes
    if (this.smells) {
      return 'This flower smells amazing!';
    } else {
      return 'What a noxious weed!';
    }
  },
  describe: function() {
    console.log("This flower is " + this.color + ".");    
  }
}
```

> Note: Methods can also access properties within the object with the `this` identifier and dot or bracket notation.

<!--Actually 11:32 -->
### Quick Challenge - Wilt & water
<!--WDI4 10:35 when starting challenge -->
<!-- 10:30 10 minutes-->
- Create a wilt() method in the prototype that decrements each flower by one petal. :(
- Create a water() method in the prototype that increments each flower by one petal. :)

<!--WDI5 10:33 -->
<!--Actually 11:43 -->
<!--10:44 WDI4 -->
## Customization
<!-- 10:40 10 minutes-->
Wouldn't it be nice if at the moment we instantiate a flower we could also define its properties?

```javascript
let chrysanthemum = new Flower("pink", 65, false);
```

Such that the `chrysanthemum` is pink with 65 petals and doesn't smell good.

#### Challenge

How could we refactor the original flower constructor to accomplish this?

> Hint: Remember a Constructor is a function, so how could we handle those values in the parentheses above?

<!--
```javascript
function Flower(color, petals, smells) {
    this.color = color;
    this.petals = petals;
    this.smells = smells;
}
```
-->

<!--WDI5 10:41 -->
<!--WDI4 11:01 when done (few questions)-->

<!--Part Two -->

<!-- Pass out flowers during break-->

## Modeling Flowers
<!--WDI5 10:55 -->
<!--Actually 11:57 -->
<!--11:11 WDI4 -->
<!-- 11:00 15 minutes-->

<!--Stress that they should NOT copy or paste, but you can put some code on the projector -->

Take a few minutes to create a flower instance based on the flower on your table, using a constructor function. Decide:

- The type of flower
- The flower's main color
- The number of petals
- Whether or not it smells pretty.
- At least one other property
- At least one method (where should the method go?)

Remember to test early, and test often, to make sure your flower Object looks the way you want.

Now take another few minutes to create a flower instance based on your neighbor's flower, using a constructor function.

## Cross-Pollination

<!--WDI5 11:09 -->
<!--WDI4 11:26 -->
<!--If we are tight on time, just drop this section entirely -->
<!--Actually 12:13 -->
<!-- 11:15 10 minutes-->

Now that we are awesome Flower experts, let's try our hand at cross-pollinating two flower objects. Cross-pollinating is beyond the realm of an individual flower and could therefore live on the Flower constructor itself.

<!-- CFU (as class), how might we declare this method, knowing what we know now?  Think-pair-share (guessing they'd say put it in prototype)  There is only one problem with that...how does that method know about any other flowers?  In order to do that, we need to go *above* the flowers.-->

To accomplish cross-pollination, we will have to create a **static method**.

The **static method** (also sometimes refered to as a **class method**) we will create is called `crossPollinate`. It is different from the instance methods we've been making (e.g. `bloom`), because it is based around the *general idea* of a flower, not a specific *instance* of a flower.  This method will:
- Take two flower instances as arguments.    
- Return a new flower instance that is a mix of both "parent" colors. (e.g. red, yellow = "red-yellow"; we don't care about the color wheel).
- Make the new petal count an average between the two parents' petal counts.
- The smellPretty gene is recessive, unfortunately. This means that a flower will smell pretty IF and only IF both flowers smell pretty.  

<!--Walk through this with class -->

<details>
<summary>Example solution</summary>

```javascript
// constructor
function Flower(color, petals, smells) {
    this.color = color;
    this.petals = petals;
    this.smells = smells;
}

// static methods
Flower.crossPollinate = function(momFlower, dadFlower) {
  let color = momFlower.color + "-" + dadFlower.color;
  let petals = (momFlower.petals + dadFlower.petals) / 2;
  let smells = momFlower.smells && dadFlower.smells;
  let babyFlower = new Flower(color, petals, smells);
  return babyFlower;
}

// instance methods
Flower.prototype = {
  bloom: function() {
    console.log("Look at me!");
  },
  smellsGood: function() {
    if (this.smells) {
      return 'This flower smells amazing!';
    } else {
      return 'What a noxious weed!';
    }
  },
  describe: function() {
    // Demonstrates use of local object variables
    // use `this` to access the instance's attributes
    console.log("This flower is " + this.color + ".");    
  }
}


let lily = new Flower("blue", 32, true);
let rose = new Flower("green", 12, true);

let rily = Flower.crossPollinate(rose, lily);

rily.smellsGood();
```

</details>

<!--Actually 12:25 -->
## Closing Thoughts
<!-- 11:25 5 minutes -->

<!-- Closing: Almost everything in Javascript either is an object or inherits from an object.  As you walk around the outside world, start thinking "how could I put that thing in JSON notation?".  What properties do people on the train have?  What about the train itself?  That's how most Javascript developers think, to one degree or another.  I want to create a game, or an app, how would I model all my objects? -->

* Why is using a prototype useful?
* Would you typically put methods or properties in the prototype?
* When would we use static methods?

<!--WDI4 11:47 -->
<!--WDI5 11:32 -->

Further Suggested Reading:
<!-- Open these so people know they're there -->
- [MDN on OOP](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Introduction_to_Object-Oriented_JavaScript)
- [MDN on Prototypal Inheritance](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)

## Licensing
All content is licensed under a CC­BY­NC­SA 4.0 license.
All software code is licensed under GNU GPLv3. For commercial use or alternative licensing, please contact legal@ga.co.
