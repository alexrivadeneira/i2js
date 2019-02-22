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
		<li>to go on vacation</li>
		<li>to drive less</li>
		<li>to get good at javascript</li>
		<li>to visit the moon</li>
		<li>peace on earth</li>
	</ul>

	<a href="http://www.duckduckgo.com">Search the Web</a>
	<script>
	</script>

</body>
</html>
```

## document.querySelector
In our demo, we change parts of the page based on a user interaction.  If we want to select some part of the page, namely a document object, to change in some way, we can use ```document.querySelector```.

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
var selectedH1 = document.querySelector('h1');
```

## Changing the layout/style/state of the page using javascript
When we first load the webpage, the initial "painting" of styles reads from the inline ```<style>``` section of our document.   We can use JavaScript after the initial loading of the page to further modify our document.  [See this diagram for a closer look at what's happening here](https://docs.google.com/presentation/d/1gCQujl8nNOSKcYDEfSqyhtc5G9yHLZO4H4s1rpeu8-4/edit?usp=sharing)

### Using classes to mark things on the page
If we have multiple ```h1``` elements on our page, we need a better way to target specific ones using querySelector.  Let's add classes to do that.

### Updating the position of something on the page
Let's add a red orb to our page, and we'll make it move around using JavaScript!

Let's add CSS to specify how a class "redBall" appears on the initial page load:
```
.redBall{
	background: red;
	border-radius: 100%;
	height: 100px;
	left: 0;
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

Using the Chrome Dev tools, let's find the position of the ball:

```
document.querySelector('.redBall').left;
```

Where does this initial left position come from?

Now let's update it:
```
document.querySelector('.redBall').left = "100px";
```
