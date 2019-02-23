## Part 2 Outline

### Today's goals
* Learn to access DOM elements (document objects) using document.querySelector
* Change the layout/state of a webpage using JavaScript

### As you come in:

* Navigate to [nerdyperson.com](http://www.nerdyperson.com) (This webpage) 🤓
* Examine HTML document: How will this page render in the browser?

```
<!DOCTYPE html>
<html>
<head>
	<title>Selecting DOM Elements Lab</title>
	<style>
		body{
			font-family: sans-serif;
			background: green;
		}
		h1{
			text-align: center;
			background: blue;
			color: white;
		}
		ul{
			background: yellow;
		}
		a{
			background: red;
			color: white;
		}
	</style>
</head>
<body>
	<h1>Welcome to my cool website</h1>

	<h2>My wishlist</h2>
	<ul>
		<li>go on vacation</li>
		<li>drive less</li>
		<li>get good at javascript</li>
		<li>visit the moon</li>
		<li>peace on earth</li>
	</ul>

	<h1>Links to Other Sites</h1>
	<a href="http://www.duckduckgo.com">Search the Web</a>
	<script>
	</script>

</body>
</html>
```

## document.querySelector
In our demo, we change parts of the page based on a user interaction.  If we want to select some part of the page, namely a **document object**, to change in some way, we can use the ```document.querySelector``` function.

Save the HTML document from above, and open it in Google Chrome.  Also open the JavaScript console.
Remember, here's the keyboard shortcut for opening the Chrome Developer Tools / JavaScript Console: ```Control + Shift + J``` on PC on ```Command + Option + J``` on Mac.

Let's select some part of the page using the JavaScript console.

A query is a kind of request. If we want to request the  ```h1``` element on the page, we can write a querySelector invocation like this:

```
document.querySelector('h1');
```
Type that into the JavaScript console on the template page from above.  You should see a Document Object being returned that references the ```h1``` element in the page.

Try selecting other elements on the webpage:
```
document.querySelector('h1');
document.querySelector('body');
document.querySelector('ul');
```

Once you have access to a document object using query selector, you can change whatever you'd like about that element!

```
document.querySelector('body').style.backgroundColor = "black";
```
Use that same construction to make changes to the other elements on the page via the JavaScript console.

Experiment with other style changes:
```
document.querySelector('h1').style.borderRadius = "100%";
document.querySelector('ul').style.fontSize = "70px";
document.querySelector('').style.fontSize = "70px";

```

What if we want to make multiple changes to the same element?
**Exercise** Use ```document.querySelector``` to make the following transformations to the ```h1``` element on the page:
1. select the h1 element
2. make the font-size 60px (fontSize)
3. background color yellow (backgroundColor)
4. add 5px margin around the element (margin)
5. add a border (border, example: "3px solid blue")

## Putting variable assignments to work
Let's move all of our JavaScript for transforming the ```h1``` element over to the ```<script>``` section of our web document.

It's a bit of a drag to have to keep writing this long construction over and over again...do we know any convenient method to store some data to access it later on?

Let's assign the result of our initial querySelector function to a variable!


```
var selectedHeader = document.querySelector('h1');
```

If we reload our page, we have access to this variable now in the console.  

```
selectedHeader.style.fontSize = '50px';
selectedHeader.style.backgroundColor = 'green';
```

## Changing the layout/style/state of the page using javascript
When we first load the webpage, the initial "painting" of styles reads from the inline ```<style>``` section of our document.   We can use JavaScript after the initial loading of the page to further modify our document.  [See this diagram for a closer look at what's happening here](https://docs.google.com/presentation/d/1gCQujl8nNOSKcYDEfSqyhtc5G9yHLZO4H4s1rpeu8-4/edit?usp=sharing)

### Using classes to mark things on the page
If we have multiple ```h1``` elements on our page, we need a better way to target specific ones using querySelector.  Let's add classes to do that.

We can add the ```class``` attribute to various HTML tags:

```
<!DOCTYPE html>
<html>
<head>
	<title>Selecting DOM Elements Lab</title>
	<style>
		body{
			font-family: sans-serif;
			background: green;
		}
		h1{
			text-align: center;
			background: blue;
			color: white;
		}
		ul{
			background: yellow;
		}
		a{
			background: red;
			color: white;
		}
	</style>
</head>
<body>
	<h1 class='mainHeader'>Welcome to my cool website</h1>

	<h2 class='wishlist'>My wishlist</h2>
	<ul class='listItems'>
		<li class='item'>go on vacation</li>
		<li class='item'>drive less</li>
		<li class='item'>get good at javascript</li>
		<li class='item'>visit the moon</li>
		<li class='item'>peace on earth</li>
	</ul>

	<h1 class='links'>Links to Other Sites</h1>
	<a class='anchor' href="http://www.duckduckgo.com">Search the Web</a>
	<script>
	</script>

</body>
</html>
```

We can use ```document.querySelector``` again, this time passing in a class string.  Class strings are the period symbol and the name of the class.  For example, if I wanted to select the ```h1``` for links on the page, I could write:

```
var linkHeader = document.querySelector('.links');
```

**Exercise**
Select and assign the following items from the updated template to variables:
1. The header at the top of the wishlist
2. The first wishlist item
3. The link on the page

### Changing the state of our page programmatically

Let's write some code to "turn off the lights" on a page.

Here's a fresh template to work with:

```
<!DOCTYPE html>
<html>
<head>
	<title>Day and Night</title>
	<style>
		body{
			font-family: sans-serif;
			background: #7f7fbf;
		}
		.celestialBody{
			borderRadius: 100%;
			background: yellow;
			width: 100px;
			height: 100px;
		}
	</style>
</head>
<body>
	<h1 class='mainHeader'>Day and Night Demo</h1>
	<div class="celestialBody"></div>
	<script>
	</script>

</body>
</html>
```

**Exercise**

1. In the script section, use querySelector to select the "celestial body" thing, the entire body, and the header.  Set each of them to different variables.
2. Refresh and open your page.  In the console, use the variables to change the color of the celestial body, the background and the header to make a "night scene".

### Saving our work

If you add your "night scene" code to the script section of your page, you're always stuck with a nighttime scene when you reload the page.  What if we want to switch between the two states? We can package our code into a function to reuse when we want.

In the script section of your page, add the following lines around your code that runs the nighttime

```
function makeItNight(){
	// replace this line with your lines of code
}
```

Now what happens when you refresh the page?

Your nighttime code hasn't run! That's because it's packaged up into a function, and will only run when you command it to!

Enter the following into the console:
```
makeItNight();
```

This invokes your code!

**Exercise**
Write more lines of code that change the page back to daytime! Package those lines into their own function.


### Updating the position of something on the page
Let's add a red orb to our page, and we'll make it move around using JavaScript!

Let's add CSS to specify how a class "redBall" appears on the initial page load:
```
.redBall{
	background: red;
	border-radius: 100%;
	height: 100px;
	left: 5px;
	position: absolute;
	top: 0;
	width: 100px;
}
```
And the HTML:
```
<div class="redBall"></div>
```
Now load your page in the browser.  

How might you guess we get the initial position of the ball?


```
var ball = document.querySelector('.redBall');
```

```
ball.style.position.left
```
would be a good guess.  However, this tells us the position of the ball **after** we make updates after the initial page load.  So, even though the ball does have a left position, it won't register here.

If you want to see the initial left position of the ball, you need to use
```
window.getComputedStyle(ball).left;
```
What gets returned?  Where does this initial number come from?

Using the Chrome Dev tools, let's set the position of the ball to a new left position:

```
var ball = document.querySelector('.redBall');
ball.style.position.left = '100px';
```

Now we can see the left position of our ball using ```ball.style.position.left``` because we've made an update after the initial page load.

**Exercise**
In the Chrome JavaScript console, make the ball move across the screen in a few steps, maybe in 100px increments.
What lines of code would you need to run?


### Updating the ball position programmatically   

Currently, we can change the left position of the ball to whatever we want.  How can we change the code to always increment the left position by some number, from wherever our starting position is, or even a new starting position after an update?

1. Get the initial ball left position on page load using ```window.getComputedStyle(ball).left``` and assign it to a variable.
2.  ```window.getComputedStyle(ball).left``` returns a string.  What happens if we try to add numbers to this string?
3. Here's a helper function you can use convert a string like "5px" to a number you can work with. Paste this function into your script so you have access to it.

```
function positionStringToInteger(pixelString){
	return parseInt(pixelString.split("px")[0]);
}
```
4. Once you have that number, you can update it....
