## Part 3 Outline

### Today's goals
* Learn to access DOM elements (document objects) using document.querySelector
* Change the layout/state of a webpage using JavaScript
* Add an event handler to the page
* Review use of functions

### As you come in:

* Navigate to [nerdyperson.com](http://www.nerdyperson.com) (This webpage) 🤓
* Complete the exercise:

## Exercise
Build an object to hold data for a ball, called ```ballData``` with the following properties
1. width, set to some number of pixels
2. height, set to some number of pixels
3. color, set to a string
4. left position, set to a number of pixels
5. top position, set to a number of pixels

In case you forgot what an object's structure looks like, here's an example object containing data about a person:
```
var person = {
	"name": "Betty",
	"age": 33,
	"occupation": "truck driver",
	"moneyInBankAccount": 999999999999,
};

```
### Moving a Ball Around the Screen Demo
We're going to use the ball object that you created for the warmup to keep track of a ball on the screen.
```
<!DOCTYPE html>
<html>
<head>
	<title>Ball Game</title>
</head>
<body>
	<script>
	</script>
</body>
</html>
```

Let's add a basic ball to our  template:

```
<!DOCTYPE html>
<html>
<head>
	<title>Ball Game</title>
	<style>
	.ballDiv{
		position: absolute;
		background: blue;
		border-radius: 100%;
		width: 50px;
		height: 50px;
		left: 0px;
		top: 0px;
		transition: left top 1s linear ease;
	}
</style>
</head>
<body>
	<div class="ballDiv"></div>

	<script>
	</script>
</body>
</html>
```

Add your ball object to the template as well - where does this variable go?

Let's update the ball's position using the ball object:

```
ball.style.top = ballData["posTop"] + 15 + "px";
```

Why does this only work one time?

We need to update the ball object's data as well!
```
ballData["posTop"] = ballData["posTop"] + 15;
```

Can we encapsulate this all into a function?

### Exericse
Create functions to move the ball in the other directions.  Test your functions by invoking them in the browser.  Remember, if we write a function called ```moveLeft``` you can invoke the code (run the code contained in the function) like this: ```moveLeft()```.

### Button
Add some button HTML elements to your page, one for each direction: left, right, up, down.  

```
<button>Your title here</button>
```

Add individual classes to each button, remember, a class attribute looks like this:
```
<button class="someClass">Your button's title</button>
```

### Event handlers
We can connect functions to specific user actions using something called an event handler.  When JavaScript detects an event running on the page, like a click, swipe, drag, mouse leave, mouse enter, focus, blur, etc. it can run a function for that event.

```
var myButton = document.querySelector('someButton');
myButton.addEventListener("click",  someFunction);
```

Can you wire your buttons to the update their position now?	

### Smoothing over transitions

Here's some CSS you can add to your moving div to make the transition a little nicer:
```
transition: left top 1s linear ease;

```

### Challenge/stretch

1. Write other functions to change the background color of the page.  Wire your function to a button using an event handler.
2. Create some boundaries for your ball.  How can you handle when your ball goes off the page or to the edge of a boundary? Experiment with the ```%``` operator (do a search for the modulus operator).
3. Can you create a second ball and prevent collisions? (don't let two balls occupy the same space or range of space in terms of their position).
4. After you create boundaries, can you figure out how to give a ball velocity and bounce it off the side of the wall?
